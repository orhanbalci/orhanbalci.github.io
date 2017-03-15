title: Java Compiler Api
link: http://orhanbalci.net/tr/?p=1421
author: admin
description: 
post_id: 1421
created: 2015/07/14 20:54:23
created_gmt: 2015/07/14 17:54:23
comment_status: open
post_name: java-compiler-api
status: publish
post_type: post

# Java Compiler Api

[java] import javax.tools.SimpleJavaFileObject; import java.io.IOException; import java.net.URI; public class JavaStringSource extends SimpleJavaFileObject { private String content; protected JavaStringSource(String uri, String content) { super(URI.create("string:///" \+ uri.replace('.', '/') + Kind.SOURCE.extension), Kind.SOURCE); this.content = content; } @Override public CharSequence getCharContent(boolean ignoreEncodingErrors) throws IOException { return content; } } [/java] [java] import javax.tools.*; import java.lang.reflect.Method; import java.net.URISyntaxException; import java.util.Arrays; import java.util.Scanner; public class Solution { public static void main(String[] args) throws URISyntaxException { String sourceCode = "public class Calculator {\n" \+ "\n" \+ " public double calculate(){\n" \+ " return %placeHolder%;" \+ " }\n" \+ "}"; Scanner scan = new Scanner(System.in); String statement = scan.nextLine(); sourceCode = sourceCode.replace("%placeHolder%", statement); if (compileInMemory(sourceCode)) { try { Class calcClass = ClassLoader.getSystemClassLoader().loadClass("Calculator"); Method m = calcClass.getDeclaredMethod("calculate"); Object calc = calcClass.newInstance(); Double ret = (Double) m.invoke(calc, null); System.out.println(ret.doubleValue()); } catch (ReflectiveOperationException e) { e.printStackTrace(); } } } private static boolean compileInMemory(String sourceCode) throws URISyntaxException { DiagnosticCollector<JavaFileObject> diagnostics = new DiagnosticCollector<JavaFileObject>(); JavaFileObject file = new JavaStringSource("Calculator", sourceCode); Iterable<? extends JavaFileObject> compilationUnits = Arrays.asList(file); JavaCompiler.CompilationTask task = ToolProvider.getSystemJavaCompiler().getTask(null, null, diagnostics, null, null, compilationUnits); boolean success = task.call(); for (Diagnostic diagnostic : diagnostics.getDiagnostics()) { System.out.println(diagnostic.getCode()); System.out.println(diagnostic.getKind()); System.out.println(diagnostic.getPosition()); System.out.println(diagnostic.getStartPosition()); System.out.println(diagnostic.getEndPosition()); System.out.println(diagnostic.getSource()); System.out.println(diagnostic.getMessage(null)); } return success; } } [/java]