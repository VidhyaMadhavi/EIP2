

# Assignment1



****

Name : Vidhya Madhavi P

Batch : 8

Date of Submission : 03 - Oct - 2018

****

[TOC]



## 1. <span style="color:blue"> Convolution:</span>

 Convolution is a process of extracting features from the input image by using a Kernel. In Convolution Neural Networks a Kernel  is run across the input image like a sliding window to extract the features of the input image.  The image on the input image can be identified by its features, convolving helps us in identifying those features. 



If the input image of size 7x7 then it is convolved with 3x3 filter/kernel with stride 1 then the output would be 5x5. If the kernel size is 3x3 then the output is always 2 less than the number of rows and columns of the input image.





![1538065935715](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538065935715.png)



Here the input image size has 4x4, as per the above explanation the output image size is 4-2 x 4-2 ie 2x2. Please refer to the explanation in the below picture.





![](Assignment1.assets/Convolution_2.png)





Convolution in image processing can have several input channels, several kernels and several convolution layers. Just like shown in the below image when the kernel is convolved the features of the input image are extracted and repeating this convolutions we form the high level features. Usually early layers captures edges and colors, and the deep layers of the CNN captures the higher level details like wheels, windows, car doors etc.



![](Assignment1.assets/1538067126176.png)





### 2. <span style="color:blue">Filters and Kernels</span>

We use Filters to extract features from input layer. Usual Kernel size is 3x3. If the input image has one channel then there is one channel for the kernel as well. If the input image has several channels like (Red, Green, Blue) then the kernel also has the same number of channels.

The 3x3 kernel has 9 numbers these are said to be weights, parameters which would be changed to improve the performance of the model. These equivalent to weights in the vanilla neural network

#### Important points to remember:

- For each kernel there is one output layer. 



![1538070914040](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538070914040.png)



![1538070382275](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538070382275.png)





## 3. <span style="color:blue">Epochs</span>

If we have 100 images as our data then running convolutions across all of the 100 images is said to be one epoch. If we repeated this process for 10 times then we said 10 epochs. Executing the whole process like (convolutions, max pooling, activation etc) once on complete input data is said to be one epoch.



#### What is the need of Epochs?

- We need to train the model very well so we perform epochs. 
- It's just like how we teach a small baby.  If we wanted to teach one year old baby about a duck then we show the duck images many times in different patterns, so after several such repetitions we expect the baby to recognize the duck when a new duck image is shown.
- To train the model well we perform epochs and with each additional epoch the accuracy and performance of the model improves, provided the training data has enough data.
- We also need to make a note that if we perform too many epochs then the model would suffer from overfitting, where during training the accuracy is very good and during testing the data the accuracy is way low. So it is important to keep in mind that we perform reasonable number of epochs. Though there is so defined number to fix the number of epochs, decision to be made as per the problem.

![1538065593279](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538065593279.png)

## 4. <span style="color:blue">1x1 convolution</span>

In 1x1 convolution the filter size is one row and one column and depth is equal to the depth of the input image. When 1x1 convolution is applied the depth of the input image is reduced to less number of layers in the output. 

![1538201696190](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538201696190.png)





![1538225050654](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538225050654.png)



In the below example we can see that 1x1 filter is applied on the input images of size 6x6 and has 5 channels and the output image size for one filter is 6x6. For each 1x1 filter one output channel is created. As there are two 1x1 filters the output image has 2 channels and each channel is of size 6x6.



![1538213183309](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538213183309.png)

## 5. <span style="color:blue">3x3 convolution</span>

In 3x3 convolution input image is convolved with 3x3 filter to extract the dimensions.  As show in the figure below the input  image has a size of 6x6 and there are 3 channels. There are 2 filters of size 3x3 and each filter has 3 channels. The number channels in the filters is always equal to number of channels in the input image. Each 3x3 filter when convolved with the input image one output channel is produced. As there are 2 filters 2 output channels are produced. As the filter size is 3x3 so the output rows are columns are 2 less than the rows and columns of the input image. Here the output image has 4 rows and 4 columns while the input image has the 6 rows and 6 columns. 





![1538070743174](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538070743174.png)



![1538210351206](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538210351206.png)

## 6. <span style="color:blue"> Feature Maps </span>

Each input image has more important features and less important features. If we need to identify an image the important features in the image need to identified for example as show in the below example to identify the image the Robot features need to be identified instead of details on the background etc. When the convolution is performed the kernel would extract the important features

- for each filter one channel is created and for each channel certain unique features are stored.
- For example one channel would identify the edges of the robot, another channel would identify the colors of the object.
- The lower level feature maps identify the edges and colors and in the higher level of feature maps has the details of the parts of the Robot like the eyes,   years, legs, hands,  button etc.





![1538066359313](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538066359313.png)



## 7. <span style="color:blue">Feature Engineering</span>

Feature Engineering is nothing but selecting the input features, which will help us to do the right prediction. The process of selecting features is said to be Feature Engineering.

In my understanding Machine learning or Deep learning algorithms are successful or a failure depending on the kind of features they have selected. If the features that are selected are very important to the given problem then the prediction is more accurate and feature selection is not appropriate then the accuracy of prediction is bad.

Feature selection can be done in many ways. For a given problem if there are too many features they can cause problems like becoming noise and do overfitting. In such scenarios some methods like dimensionality reduction need to be applied to reduce the number of features and as a result the importance features can be processed.

With respect to Computer vision there will lot of input features and it would lot of time to process these features with machine learning algorithms. With Deep Neural Networks the processing has become more workable. CNN is one such method to extract features in computer vision.



## 8. <span style="color:blue"> Activation Function</span>



The activation function is used to decide whether a particular node has to be trigged or not.



![1538221767492](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538221767492.png)



## 9. <span style="color:blue">How to create an account on Github and Upload a sample project</span>









## 10. <span style="color:blue">Receptive Field</span>

Receptive field is a cell which indicate how much area of the image can be seen.



In the figure below we see that 



![1538499726281](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538499726281.png)





![1538057273021](C:\Users\vidhya\AppData\Roaming\Typora\typora-user-images\1538057273021.png)

## 11. <span style="color:blue"> Examples of use of MathJax in Markdown</span>



Use `$$\begin{matrix}…\end{matrix}$$` In between the `\begin` and `\end`, put the matrix elements. End each matrix row with `\\`, and separate matrix elements with `&`. For example,



1. To add brackets, either use `\left…\right` as in section 6 of the tutorial, or replace `matrix` with `pmatrix` (1324)(1234), `bmatrix` [1324][1234], `Bmatrix` {1324}{1234}, `vmatrix` ∣∣∣1324∣∣∣|1234|, `Vmatrix` ∥∥∥1324∥∥∥‖1234‖.

2. Use `\cdots` ⋯⋯ `\ddots` ⋱⋱ `vdots` ⋮⋮ when you want to omit some of the entries:



   ⎛⎝⎜⎜⎜⎜⎜11⋮1a1a2⋮ama21a22⋮a2m⋯⋯⋱⋯an1an2⋮anm⎞⎠⎟⎟⎟⎟⎟


dsdsadsd

\(ax^2 + bx + c = 0\)

For horizontally "augmented" matrices, put parentheses or brackets around a suitably-formatted table; see [arrays](http://meta.math.stackexchange.com/a/5044/) below for details. Here is an example:



[142536][123456]



is produced by:

```
$$ \left[
\begin{array}{cc|c}
  1&2&3\\
  4&5&6
\end{array}
\right] $$
```

$$x = {-b \pm \sqr
t{b^2-4ac} \over 2a}.$$





 	



$$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$



To write mean formula = square(x-xbar)  / sigma





For **Greek letters**, use `\alpha`, `\beta`, …, `\omega`: α,β,…ωα,β,…ω. For uppercase, use `\Gamma`, `\Delta`, …, `\Omega`: Γ,Δ,…,ΩΓ,Δ,…,Ω.



For **superscripts and subscripts**, use `^` and `_`. For example, `x_i^2`: x2ixi2, `\log_2 x`: log2xlog2⁡x.





1. **Groups**. Superscripts, subscripts, and other operations apply only to the next “group”. A “group” is either a single symbol, or any formula surrounded by curly braces `{`…`}`. If you do `10^10`, you will get a surprise: 10101010. But `10^{10}` gives what you probably wanted: 10101010. Use curly braces to delimit a formula to which a superscript or subscript applies: `x^5^6` is an error;`{x^y}^z` is xyzxyz, and `x^{y^z}` is xyzxyz. Observe the difference between `x_i^2` x2ixi2 and `x_{i^2}` xi2xi2.

2. **Parentheses** Ordinary symbols `()[]` make parentheses and brackets (2+3)[4+4](2+3)[4+4]. Use `\{` and `\}` for curly braces {}{}.

   These do *not* scale with the formula in between, so if you write `(\frac{\sqrt x}{y^3})` the parentheses will be too small: (x√y3)(xy3). Using `\left(`…`\right)` will make the sizes adjust automatically to the formula they enclose: `\left(\frac{\sqrt x}{y^3}\right)` is (x√y3)(xy3).

   `\left` and`\right` apply to all the following sorts of parentheses: `(` and `)` (x)(x), `[` and `]` [x][x], `\{` and `\}` {x}{x}, `|` |x||x|, `\vert` |x||x|, `\Vert` ∥x∥‖x‖, `\langle` and `\rangle` ⟨x⟩⟨x⟩, `\lceil`and `\rceil` ⌈x⌉⌈x⌉, and `\lfloor` and `\rfloor` ⌊x⌋⌊x⌋. `\middle` can be used to add additional dividers. There are also invisible parentheses, denoted by `.`: `\left.\frac12\right\rbrace` is 12}12}.

3. f manual size adjustments are required: `\Biggl(\biggl(\Bigl(\bigl((x)\bigr)\Bigr)\biggr)\Biggr)` gives (((((x)))))(((((x))))).

4. **Sums and integrals** `\sum` and `\int`; the subscript is the lower limit and the superscript is the upper limit, so for example `\sum_1^n` ∑n1∑1n. Don't forget `{`…`}` if the limits are more than a single symbol. For example, `\sum_{i=0}^\infty i^2` is ∑∞i=0i2∑i=0∞i2. Similarly, `\prod` ∏∏, `\int` ∫∫, `\bigcup` ⋃⋃, `\bigcap` ⋂⋂, `\iint` ∬∬, `\iiint` ∭∭.

5. **Fractions** There are [three ways to make these](https://math.meta.stackexchange.com/q/12978/3111). `\frac ab` applies to the next two groups, and produces abab; for more complicated numerators and denominators use `{`…`}`: `\frac{a+1}{b+1}` is a+1b+1a+1b+1. If the numerator and denominator are complicated, you may prefer `\over`, which splits up the group that it is in: `{a+1\over b+1}` is a+1b+1a+1b+1. Using `\cfrac{a}{b}` command is useful for continued fractions abab, more details for which [are given in this sub-article](https://math.meta.stackexchange.com/a/5058/3111).

- `\lt \gt \le \leq \leqq \leqslant \ge \geq \geqq \geqslant \neq` <>≤≤≦⩽≥≥≧⩾≠<>≤≤≦⩽≥≥≧⩾≠. You can use `\not` to put a slash through almost anything: `\not\lt` ≮≮ but it often looks bad.
- `\times \div \pm \mp` ×÷±∓×÷±∓. `\cdot` is a centered dot: x⋅yx⋅y
- `\cup \cap \setminus \subset \subseteq \subsetneq \supset \in \notin \emptyset \varnothing` ∪∩∖⊂⊆⊊⊃∈∉∅∅∪∩∖⊂⊆⊊⊃∈∉∅∅
- `{n+1 \choose 2k}` or `\binom{n+1}{2k}` (n+12k)(n+12k)
- `\to \rightarrow \leftarrow \Rightarrow \Leftarrow \mapsto` →→←⇒⇐↦→→←⇒⇐↦
- `\land \lor \lnot \forall \exists \top \bot \vdash \vDash` ∧∨¬∀∃⊤⊥⊢⊨∧∨¬∀∃⊤⊥⊢⊨
- `\star \ast \oplus \circ \bullet` ⋆∗⊕∘∙⋆∗⊕∘∙
- `\approx \sim \simeq \cong \equiv \prec \lhd \therefore` ≈∼≃≅≡≺⊲∴≈∼≃≅≡≺⊲∴
- `\infty \aleph_0` ∞ℵ0∞ℵ0 `\nabla \partial` ∇∂∇∂ `\Im \Re` IRℑℜ
- For modular equivalence, use `\pmod` like this: `a\equiv b\pmod n` a≡b(modn)a≡b(modn).
- `\ldots` is the dots in a1,a2,…,ana1,a2,…,an `\cdots` is the dots in a1+a2+⋯+ana1+a2+⋯+an
- Some Greek letters have variant forms: `\epsilon \varepsilon` ϵεϵε, `\phi \varphi` ϕφϕφ, and others. Script lowercase l is `\ell` ℓℓ.

[Detexify](http://detexify.kirelabs.org/classify.html) lets you draw a symbol on a web page and then lists the TEXTEX symbols that seem to resemble it. These are not guaranteed to work in MathJax but are a good place to start. To check that a command is supported, note that MathJax.org maintains a [list of currently supported LATEXLATEX commands](http://docs.mathjax.org/en/latest/tex.html#supported-latex-commands), and one can also check Dr. Carol JVF Burns's page of [TEXTEXCommands Available in MathJax](http://www.onemathematicalcat.org/MathJaxDocumentation/TeXSyntax.htm).





1. **Spaces** MathJax usually decides for itself how to space formulas, using a complex set of rules. Putting extra literal spaces into formulas will not change the amount of space MathJax puts in: `a␣b` and `a␣␣␣␣b` are both abab. To add more space, use `\,` for a thin space abab; `\;` for a wider space abab. `\quad` and `\qquad` are large spaces: abab, abab.

   To set plain text, use `\text{…}`: {x∈s∣x is extra large}{x∈s∣x is extra large}. You can nest `$…$` inside of `\text{…}`.

2. **Accents and diacritical marks** Use `\hat` for a single symbol x^x^, `\widehat` for a larger formula xyˆxy^. If you make it too wide, it will look silly. Similarly, there are `\bar` x¯x¯ and `\overline` xyz¯¯¯¯¯¯¯¯xyz¯, and `\vec` x⃗ x→ and `\overrightarrow` xy−→xy→ and `\overleftrightarrow` xy←→xy↔. For dots, as in ddxxx˙=x˙2+xx¨ddxxx˙=x˙2+xx¨, use `\dot` and `\ddot`.

3. Special characters used for MathJax interpreting can be escaped using the `\` character: `\$` $$, `\{` {{, `\_` __, etc. If you want `\` itself, you should use `\backslash` ∖∖, because `\\` is for a new line.








































