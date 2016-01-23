# The Learning Problem

标签（空格分隔）： reading

---

1. learning vernus Design    
2. learning vernus memorizing
3. Outside the Data Set
>Since we maintain that $f$ is an unknown function, we can prove that $f$ remains unknown outside of ${\cal D}$  

4. Empirical $\mit v$ vernus true $\mu$
>$\qquad$ To quantify the relationship between $\mit v$ and $\mu$, we use a simple bound called the $\cal Hoeffding Inequality$
>It  states that for any sample size $\mit N$,    
\begin{equation}
\Bbb P[|v - \mu| > \epsilon] \le 2\mit e^{-2\epsilon^2\mit N } \qquad \text{for any}\space \epsilon \lt 0
\label{eq:hoeffding}
\end{equation}
$\qquad$ Here,   $\Bbb P[.]$ denotes the probability of an event, $\epsilon$ is any positive value. It says that as the sample size $N$ grows, it becomes exponentially unlikely that $\nu$ will deviate from $\mu$ by more than our "tolerance" $\epsilon$.   
$\qquad$ The only  quantity that is random in \eqref{eq:hoeffding} is $\nu$ which depends on the random sample. By contract, $\mu$ is not random. It's just a constant, albeit unknown to us. There is a subtle point here. The utility of \eqref{eq:hoeffding} is to infer the value of $\mu$ using the value of $\nu$, although it is $\mu$ that affects $\nu$, not vice versa. However, since the effect is that $\nu$ tends to be close to $\mu$, we infer that $\mu$ "tends" to be close to $\nu$.  
$\qquad$ Alghough $\Bbb P$$[|\nu - \mu| > \epsilon]$ depends on $\mu$, as $\mu$ appears in the argument and also affects the distribution of $\nu$, we are able to bound the probability by $2\mit e^{-2\epsilon^2\mit N}$ which does not depend on $\mu$.   

$\qquad$ The training examples play the role of a sample from the bin. If the inputs $\bf x_1, ...,\bf x_N$ in $\cal D$ are picked independently according to $\cal P$, we will get a random sample of red($h(\bf x_\cal n) \neq f(\bf x_\cal n)$) and green ($h(\bf x_\cal n) = f(\bf x_\cal n)$) points. Each point will be red with probability $\mu$ and green with probability $1-\mu$.

![1.11.png-121.4kB][1]

\begin{equation}
\Bbb P[|E_{\text{in}}(g) - E_{\text{out}}(g)| > \epsilon] \le 2M\mit e^{-2\epsilon^2\mit N } 
\label{eq:surrogatehoeffding}
\end{equation}    

The feasibility of learning is split into two sub-questions:   
> 1. Can we make sure that $E_{\text{in}}(g)$ is close enough to $E_{\text{out}}(g)$?
2. Can we make $E_{\text{in}}(g)$ small enough?

With complex hypotheses $\cal H$, $M$ is large, the bound would loose. While we need a complex $\cal H$, this gives a more flexibility in finding some $g$ that fits the data well.

The complexity of $f$ does not affect the first question. However, it needs more training sample to ensure $E_{\text{in}}(g)$ is small enough.

References: 
[1][Markdown](https://www.zybuluo.com/codeep/note/163962)


  [1]: http://static.zybuluo.com/ivertime/sjy8dygo1suzqasump5khgwp/1.11.png
