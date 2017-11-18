# Repositório para a palestra no XIV-FGSL
# Título: Introdução ao processamento de dados com Hadoop MapReduce.
# Instruções para executar os códigos.
Assume-se que os dados já estão no HDFS em:
```bash
/wordcount/input.txt
```
Para gerar o JAR é preciso ter no .bashrc as seguintes variáveis:
```bash
export JAVA_HOME=/path/para/o/java
export PATH=${JAVA_HOME}/bin:${PATH}
export HADOOP_CLASSPATH=${JAVA_HOME}/lib/tools.jar
```

Compile WordCount.java e crie o jar:
```bash
hadoop com.sun.tools.javac.Main WordCount.java
jar cf wordcount.jar WordCount*.class
```

Para rodar o JAR:
```bash
yarn jar wordcount.jar WordCount /wordcount/input.txt /wordcount/output
```

Para ver o resultado:
```bash
hdfs dfs -cat /wordcount/output/part-r-00000
```
