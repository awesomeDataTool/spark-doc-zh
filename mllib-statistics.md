---
layout: global
title: Basic Statistics - RDD-based API
displayTitle: Basic Statistics - RDD-based API
---

* Table of contents
{:toc}


`\[
\newcommand{\R}{\mathbb{R}}
\newcommand{\E}{\mathbb{E}}
\newcommand{\x}{\mathbf{x}}
\newcommand{\y}{\mathbf{y}}
\newcommand{\wv}{\mathbf{w}}
\newcommand{\av}{\mathbf{\alpha}}
\newcommand{\bv}{\mathbf{b}}
\newcommand{\N}{\mathbb{N}}
\newcommand{\id}{\mathbf{I}}
\newcommand{\ind}{\mathbf{1}}
\newcommand{\0}{\mathbf{0}}
\newcommand{\unit}{\mathbf{e}}
\newcommand{\one}{\mathbf{1}}
\newcommand{\zero}{\mathbf{0}}
\]`

## Summary statistics
����ͨ������Statistics���colStatsΪRDD[Vector]�����ṩͳ�ƻ�����Ϣ��


<div class="codetabs">
<div data-lang="scala" markdown="1">

[`colStats()`](api/scala/index.html#org.apache.spark.mllib.stat.Statistics$) ����
[`MultivariateStatisticalSummary`](api/scala/index.html#org.apache.spark.mllib.stat.MultivariateStatisticalSummary)��ʵ���а��������С��ƽ��ֵ���������Ԫ�ͺϼƵ�ͳ����Ϣ,


����� [`MultivariateStatisticalSummary` Scala docs](api/scala/index.html#org.apache.spark.mllib.stat.MultivariateStatisticalSummary) �鿴��ϸAPI.

{% include_example scala/org/apache/spark/examples/mllib/SummaryStatisticsExample.scala %}
</div>

<div data-lang="java" markdown="1">

[`colStats()`](api/java/org/apache/spark/mllib/stat/Statistics.html)  ����
[`MultivariateStatisticalSummary`](api/scala/index.html#org.apache.spark.mllib.sta
[`MultivariateStatisticalSummary`](api/java/org/apache/spark/mllib/stat/MultivariateStatisticalSummary.html)��ʵ���а��������С��ƽ��ֵ���������Ԫ�ͺϼƵ�ͳ����Ϣ,


����[`MultivariateStatisticalSummary` Java docs](api/java/org/apache/spark/mllib/stat/MultivariateStatisticalSummary.html) �鿴��ϸAPI.

{% include_example java/org/apache/spark/examples/mllib/JavaSummaryStatisticsExample.java %}
</div>

<div data-lang="python" markdown="1">
[`colStats()`](api/python/pyspark.mllib.html#pyspark.mllib.stat.Statistics.colStats) ����
[`MultivariateStatisticalSummary`](api/python/pyspark.mllib.html#pyspark.mllib.stat.MultivariateStatisticalSummary)��ʵ���а��������С��ƽ��ֵ���������Ԫ�ͺϼƵ�ͳ����Ϣ.

���� [`MultivariateStatisticalSummary` Python docs](api/python/pyspark.mllib.html#pyspark.mllib.stat.MultivariateStatisticalSummary) �鿴��ϸAPI.

{% include_example python/mllib/summary_statistics_example.py %}
</div>

</div>

## Correlations �����

�ڻ���ͳ���м����������ݵ��������ͨ�õĲ�����������`spark.mllib`�ṩ�˼����������������ص����API.Ŀǰ��������Եķ���֧��Ƥ��ѷϵ����˹Ƥ����ϵ����


<div class="codetabs">
<div data-lang="scala" markdown="1">
[`Statistics`](api/scala/index.html#org.apache.spark.mllib.stat.Statistics$)�ṩ����������֮������Եķ�����
������������ͣ�����`RDD[Double]` ����һ�� `RDD[Vector]`�����ֱ��Ӧ`Double`������
`Matrix`

����[`Statistics` Scala docs](api/scala/index.html#org.apache.spark.mllib.stat.Statistics$) ��API�ĵ��л�ȡ��ϸ��Ϣ��

{% include_example scala/org/apache/spark/examples/mllib/CorrelationsExample.scala %}
</div>

<div data-lang="java" markdown="1">
[`Statistics`](api/java/org/apache/spark/mllib/stat/Statistics.html)�ṩ����������֮������Եķ�����
������������ͣ�����`JavaDoubleRDD` ����һ�� `JavaRDD<Vector>`�����ֱ��Ӧ`Double`������
`Matrix`

���� [`Statistics` Java docs](api/java/org/apache/spark/mllib/stat/Statistics.html) ��API�ĵ��л�ȡ��ϸ��Ϣ.

{% include_example java/org/apache/spark/examples/mllib/JavaCorrelationsExample.java %}
</div>

<div data-lang="python" markdown="1">
[`Statistics`](api/python/pyspark.mllib.html#pyspark.mllib.stat.Statistics)�ṩ����������֮������Եķ�����
������������ͣ�����`RDD[Double]` ����һ�� `RDD[Vector]`�����ֱ��Ӧ`Double`������`Matrix`

���� [`Statistics` Python docs](api/python/pyspark.mllib.html#pyspark.mllib.stat.Statistics) ��API�ĵ��л�ȡ��ϸ��Ϣ.

{% include_example python/mllib/correlations_example.py %}
</div>

</div>

## Stratified sampling




������`spark.mllib`���л���ͳ�Ƶĺ�����ͬ��`sampleByKey` and `sampleByKeyExact`�ȷֲ��������������key-value �Ե�RDD��ʹ�á�
���ڷֲ���������Խ�keys������ǩ��value��������������key ��������Ů�����ĵ�id�����Ե�value�������˿�ͳ�Ƶ��б�����ĵ��еĴʻ��
`sampleByKey`��������Ӳ�ҵķ��������Ƿ���в����������Ҫһ�ι������������ݣ����ṩһ��*����*������С��`sampleByKeyExact`��Ҫ��`sampleByKey`��ʹ�õ�ÿ����������ʹ�ø������Դ�����ṩ�ڲ�����С�Ͻ�����99.99%���Ŷȵľ�ȷ������
`sampleByKeyExact`Ŀǰ��python api �в�֧�֡�

<div class="codetabs">
<div data-lang="scala" markdown="1">
[`sampleByKeyExact()`](api/scala/index.html#org.apache.spark.rdd.PairRDDFunctions) �����û���ȷ����
 $\lceil f_k \cdot n_k \rceil \, \forall k \in K$ ��,  $f_k$ ��key $k$ �����ķ���, $n_k$ ��key $k$ ��K-V������, $K$ key�ļ��ϡ�
 �޷Żس�����Ҫһ��RDD�ϵĸ��ӹ��˱�֤������С�����ַŻس�����Ҫ�������ӹ��ˡ�

{% include_example scala/org/apache/spark/examples/mllib/StratifiedSamplingExample.scala %}
</div>

<div data-lang="java" markdown="1">
[`sampleByKeyExact()`](api/java/org/apache/spark/api/java/JavaPairRDD.html) �����û���ȷ����
 $\lceil f_k \cdot n_k \rceil \, \forall k \in K$ ��,  $f_k$ ��key $k$ �����ķ���, $n_k$ ��key $k$ ��K-V������, $K$ key�ļ��ϡ�
 �޷Żس�����Ҫһ��RDD�ϵĸ��ӹ��˱�֤������С�����ַŻس�����Ҫ�������ӹ��ˡ�

{% include_example java/org/apache/spark/examples/mllib/JavaStratifiedSamplingExample.java %}
</div>
<div data-lang="python" markdown="1">
[`sampleByKey()`](api/python/pyspark.html#pyspark.RDD.sampleByKey) �����û���ȷ����
 $\lceil f_k \cdot n_k \rceil \, \forall k \in K$ ��,  $f_k$ ��key $k$ �����ķ���, $n_k$ ��key $k$ ��K-V������, $K$ key�ļ��ϡ�
 �޷Żس�����Ҫһ��RDD�ϵĸ��ӹ��˱�֤������С�����ַŻس�����Ҫ�������ӹ��ˡ�

*Note:* `sampleByKeyExact()` is currently not supported in Python.

{% include_example python/mllib/stratified_sampling_example.py %}
</div>

</div>

## Hypothesis testing
��������������жϽ���Ƿ����ͳ��ѧ���塢���ֽ���Ƿ�żȻ�������������ߡ�`spark.mllib`Ŀǰ֧��Ƥ��ѷ����( $\chi^2$)����
������֤����ŶȺͶ����Լ��顣�������;���������ŶȻ�����Բ����Ƿ���С�����Ŷ�Ҫ���������ͱ�����`Vector`���������Լ���
Ҫ�����������`Matrix`
`spark.mllib` Ҳ֧����������`RDD[LabeledPoint]`��ͨ��������������Լ���������ѡ��

<div class="codetabs">
<div data-lang="scala" markdown="1">
[`Statistics`](api/scala/index.html#org.apache.spark.mllib.stat.Statistics$) �ṩ��������Ƥ��ѷ�������顣���������չʾ��
������кͽ��Ϳ������顣

{% include_example scala/org/apache/spark/examples/mllib/HypothesisTestingExample.scala %}
</div>

<div data-lang="java" markdown="1">
[`Statistics`](api/java/org/apache/spark/mllib/stat/Statistics.html)�ṩ��������Ƥ��ѷ�������顣���������չʾ��
������кͽ��Ϳ������顣

���� [`ChiSqTestResult` Java docs](api/java/org/apache/spark/mllib/stat/test/ChiSqTestResult.html) ��API �л�ȡ��ϸ��Ϣ.

{% include_example java/org/apache/spark/examples/mllib/JavaHypothesisTestingExample.java %}
</div>

<div data-lang="python" markdown="1">
[`Statistics`](api/python/index.html#pyspark.mllib.stat.Statistics$) �ṩ��������Ƥ��ѷ�������顣���������չʾ��
������кͽ��Ϳ������顣

���� [`Statistics` Python docs](api/python/pyspark.mllib.html#pyspark.mllib.stat.Statistics) ��API �л�ȡ��ϸ��Ϣ.

{% include_example python/mllib/hypothesis_testing_example.py %}
</div>

</div>
���⣬`spark.mllib`�ṩ�˼������ĳ�ֲַ���Kolmogorov Smirnov��KS�������1������2���ʵ�֡�
�ṩ���۷ֲ������ƣ�Ŀǰ��֧����̫�ֲ����Ͳ������߸������۷ֲ������ۼƷֲ��������û����Լ������ǵ������Ӹ÷ֲ��г�ȡ��ԭ���衣
������û��Ե���̬�ֲ��ļ����в�û���ṩ�ֲ��Ĳ����������ʼ����׼��̬�ֲ�����¼���ʵ�����Ϣ��
<div class="codetabs">
<div data-lang="scala" markdown="1">
[`Statistics`](api/scala/index.html#org.apache.spark.mllib.stat.Statistics$) �ṩ������ִ��
Kolmogorov Smirnov��KS�������1������2��ļ���. ���������չʾ��������к���������顣

���� [`Statistics` Scala docs](api/scala/index.html#org.apache.spark.mllib.stat.Statistics$) ��API �л�ȡ��ϸ��Ϣ.

{% include_example scala/org/apache/spark/examples/mllib/HypothesisTestingKolmogorovSmirnovTestExample.scala %}
</div>

<div data-lang="java" markdown="1">
[`Statistics`](api/java/org/apache/spark/mllib/stat/Statistics.html) �ṩ������ִ��
Kolmogorov Smirnov��KS�������1������2��ļ���. ���������չʾ��������к���������顣

����  [`Statistics` Java docs](api/java/org/apache/spark/mllib/stat/Statistics.html) ��API �л�ȡ��ϸ��Ϣ.

{% include_example java/org/apache/spark/examples/mllib/JavaHypothesisTestingKolmogorovSmirnovTestExample.java %}
</div>

<div data-lang="python" markdown="1">
[`Statistics`](api/python/pyspark.mllib.html#pyspark.mllib.stat.Statistics) �ṩ������ִ��
Kolmogorov Smirnov��KS�������1������2��ļ���. ���������չʾ��������к���������顣

����  [`Statistics` Python docs](api/python/pyspark.mllib.html#pyspark.mllib.stat.Statistics) ��API �л�ȡ��ϸ��Ϣ.

{% include_example python/mllib/hypothesis_testing_kolmogorov_smirnov_test_example.py %}
</div>
</div>

### Streaming Significance Testing
`spark.mllib` �ṩ����ʽ���Ե�ʵ����֧�ַ������������
��Щ������������Spark Streaming ��`DStream[(Boolean,Double)]`�����ϣ�Ԫ��ĵ�һ��Ԫ�ر�ʾ������(`false`) ����ʵ����(`true`),Ԫ��ĵڶ���Ԫ���ǹ۲�ֵ
��ʽ�������Լ���֧�����²�����

* `peacePeriod` - ���Զ��ٳ�ʼ����������������ֵ��Ӱ�졣
* `windowSize` - The number of past batches to perform hypothesis һ��������������������������Ϊ'0'����֮ǰ�������εĵ������ۼƴ���


<div class="codetabs">
<div data-lang="scala" markdown="1">
[`StreamingTest`](api/scala/index.html#org.apache.spark.mllib.stat.test.StreamingTest)
�ṩ��ʽ�ļ������.

{% include_example scala/org/apache/spark/examples/mllib/StreamingTestExample.scala %}
</div>

<div data-lang="java" markdown="1">
[`StreamingTest`](api/java/index.html#org.apache.spark.mllib.stat.test.StreamingTest)
�ṩ��ʽ�ļ������.

{% include_example java/org/apache/spark/examples/mllib/JavaStreamingTestExample.java %}
</div>
</div>


## Random data generation
������������Ƕ�������㷨��ԭ�ͷ������ܲ��Էǳ����õĹ��ߡ�`spark.mllib`֧�ָ��ݸ����ķֲ�������ȷֲ�����׼��̬�ֲ������ɷֲ�����ȡ����ͬ�ֲ�(i.i.d)������������������RDD


<div class="codetabs">
<div data-lang="scala" markdown="1">
[`RandomRDDs`](api/scala/index.html#org.apache.spark.mllib.random.RandomRDDs$) �ṩ�������double���͵�RDD�����������͵�RDD�Ĺ���������
���������������һ�����double���ͷ��ϱ�׼��̬�ֲ�(0,1)��RDDȻ����ת��Ϊ(1,4)����̬�ֲ�


Refer to the [`RandomRDDs` Scala docs](api/scala/index.html#org.apache.spark.mllib.random.RandomRDDs$) for details on the API.

{% highlight scala %}
import org.apache.spark.SparkContext
import org.apache.spark.mllib.random.RandomRDDs._

val sc: SparkContext = ...
//�ӱ�׼��̬�ֲ�`N(0, 1)`����ȡ100�����ͬ�ֲ����double��������10��������RDD
val u = normalRDD(sc, 1000000L, 10)
//��map ���ӽ�RDD �����ת��Ϊ������̬�ֲ�`N(1, 4)`��RDD
val v = u.map(x => 1.0 + 2.0 * x)
{% endhighlight %}
</div>

<div data-lang="java" markdown="1">
[`RandomRDDs`](api/java/index.html#org.apache.spark.mllib.random.RandomRDDs) �ṩ�������double���͵�RDD�����������͵�RDD�Ĺ���������
���������������һ�����double���ͷ��ϱ�׼��̬�ֲ�(0,1)��RDDȻ����ת��Ϊ(1,4)����̬�ֲ���

Refer to the [`RandomRDDs` Java docs](api/java/org/apache/spark/mllib/random/RandomRDDs) for details on the API.

{% highlight java %}
import org.apache.spark.SparkContext;
import org.apache.spark.api.JavaDoubleRDD;
import static org.apache.spark.mllib.random.RandomRDDs.*;

JavaSparkContext jsc = ...

//�ӱ�׼��̬�ֲ�`N(0, 1)`����ȡ100�����ͬ�ֲ����double��������10��������RDD
JavaDoubleRDD u = normalJavaRDD(jsc, 1000000L, 10);
//��map ���ӽ�RDD �����ת��Ϊ������̬�ֲ�`N(1, 4)`��RDD
JavaDoubleRDD v = u.mapToDouble(x -> 1.0 + 2.0 * x);
{% endhighlight %}
</div>

<div data-lang="python" markdown="1">
[`RandomRDDs`](api/python/pyspark.mllib.html#pyspark.mllib.random.RandomRDDs) �ṩ�������double���͵�RDD�����������͵�RDD�Ĺ���������
���������������һ�����double���ͷ��ϱ�׼��̬�ֲ�(0,1)��RDDȻ����ת��Ϊ(1,4)����̬�ֲ���

���� [`RandomRDDs` Python docs](api/python/pyspark.mllib.html#pyspark.mllib.random.RandomRDDs) ��API �л�ȡ��ϸ��Ϣ��

{% highlight python %}
from pyspark.mllib.random import RandomRDDs

sc = ... # SparkContext

#�ӱ�׼��̬�ֲ�`N(0, 1)`����ȡ100�����ͬ�ֲ����double��������10��������RDD
u = RandomRDDs.normalRDD(sc, 1000000L, 10)
#��map ���ӽ�RDD �����ת��Ϊ������̬�ֲ�`N(1, 4)`��RDD#
v = u.map(lambda x: 1.0 + 2.0 * x)
{% endhighlight %}
</div>
</div>

## Kernel density estimation

[���ܶȹ���](https://en.wikipedia.org/wiki/Kernel_density_estimation) is a technique
useful for visualizing empirical probability distributions without requiring assumptions about the
particular distribution that the observed samples are drawn from. It computes an estimate of the
probability density function of a random variables, evaluated at a given set of points. It achieves
this estimate by expressing the PDF of the empirical distribution at a particular point as the
mean of PDFs of normal distributions centered around each of the samples.
���ܶȹ�����һ�ֶԿ��ӻ�������ʷֲ� ����ͨ���ܶϴ������еõ��ض��ֲ������ܶȹ�����ͨ����������������������ܶȺ�����ͨ������
һ��������������������ܶȹ���ͨ���ض���ĸ����ܶȺ�������ͨ�����ض����ﾭ��ֲ��ĸ����ܶȺ�����Ϊ��ÿ������Ϊ���ĵ���̬�ֲ��ĸ����ܶȺ�����ƽ��ֵ��ʵ���������

<div class="codetabs">

<div data-lang="scala" markdown="1">
[`KernelDensity`](api/scala/index.html#org.apache.spark.mllib.stat.KernelDensity) �ṩ�˼�������RDD�ĺ��ܶȹ��Ʒ��������������չʾ����ôʵ������

���� [`KernelDensity` Scala docs](api/scala/index.html#org.apache.spark.mllib.stat.KernelDensity) ��API �л�ȡ��ϸ��Ϣ��

{% include_example scala/org/apache/spark/examples/mllib/KernelDensityEstimationExample.scala %}
</div>

<div data-lang="java" markdown="1">
[`KernelDensity`](api/java/index.html#org.apache.spark.mllib.stat.KernelDensity) �ṩ�˼�������RDD�ĺ��ܶȹ��Ʒ��������������չʾ����ôʵ������

���� [`KernelDensity` Java docs](api/java/org/apache/spark/mllib/stat/KernelDensity.html) ��API �л�ȡ��ϸ��Ϣ��

{% include_example java/org/apache/spark/examples/mllib/JavaKernelDensityEstimationExample.java %}
</div>

<div data-lang="python" markdown="1">
[`KernelDensity`](api/python/pyspark.mllib.html#pyspark.mllib.stat.KernelDensity) �ṩ�˼�������RDD�ĺ��ܶȹ��Ʒ��������������չʾ����ôʵ������

���� [`KernelDensity` Python docs](api/python/pyspark.mllib.html#pyspark.mllib.stat.KernelDensity) ��API �л�ȡ��ϸ��Ϣ��

{% include_example python/mllib/kernel_density_estimation_example.py %}
</div>

</div>
