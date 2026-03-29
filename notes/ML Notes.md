# ML
- better with structured data
- problem => idea => solution (algo => classification)
- doesn't need explicit learning
- works with slightly small data => data = accuracy till some point => stops or declines
- doesn't need strong computational power
- can't figure out complex patterns(pics)
- Types:
	- supervised: data+features+label => student grade(interval) can be classification/regression.
		- classification: label (specified) discrete 
		- regression: numerical continuous vals
	- unsupervised: data => find pattern
		- clustering: find pattern in data
		- dimensionality reduction: compressing my data => my data has 100 dim(features) => wanna scale down the dims 
			- feature extraction: extract the features from data/add new ones
			- feature selection: select some features from extracted ones and cancel others
			- dim reduction: compress my features to work w them(numbers ain't interpretable) => cuz of projection
	- semi-supervised: train on unlabeled and test on labeled
	- self-supervised: tries t label them himself(clusters) => more in NLP(bert)
	- RL: trial & error obstacles
- Linear regression: draw line that represents the data => predict using that line
- SGD:
	- draw random lines till u get the best representing line
	- min cost/loss function => مجموع المسافات بين النقط والخط أقل ما يمكن y_actual, y_predict 
	- butttt if the point is lower than the predicted line: -val => cancel each other
	- so we get => square loss + 
	- relation between w and loss fuction => convex shape![img](<./media/Pasted image 20251201200621.png>)
	- ![img](<./media/Pasted image 20251220093img.png>)
	- cuz of using square function on loss
	- محتاج أعرف الاتجاه ال هتحرك فيه => derivative loss wr to weight![img](<./media/Pasted image 20251201200728.png>)
	- -slope = W update => optimal point(local minima) => repeat until converge (predict till converge)
	- ممكن ابديت ال weight يكون كبير لأني بعمل ابديت لكل الفيتشرز المضروبة في ال weight في معادلة الخط => علشان كدا بعمل ابديت بجزء من قيمة ال weight عن طريق ال lr(hyper parameter : معندناش اجابة صح ليها بنقعد نجرب)
	- derivative of line => direction of line
- converge: settled
	- local minima: converges wo reaching min loss
	- high lr
	- non-linear features => no pattern => no converge => max iter

- linear regression data:
	- linearity: linear data علاقة خطية بين الفيتشر والتارجت =. لو فيه شوية وشوية لا هاخد اللينيار بس
	- homoscedasticity: الأخطاء بتاعتي ملهاش باترن واضح => لو ليه باترن يبقا فيه علاقة والموديل مش عارف يكتشفها![img](<./media/Pasted image 20251201202307.png>)
		- ![img](<./media/Pasted image 20251201202331.png>)فاهم الباترن في جزء من الداتا وجزء لا على اليمين، مش متباين 
	- dependency of error: affects other errors(results of yesterday affects today's)
	- no multi co-linearity: correlation between data is high(عدد السكان وعدد البيوت) => won't understand what affects data, adapt this relation laziness
	- normality of residual: normal distro of errors
	- no outliers in linear models => 1 change in 1 number affects the whole line.
- logistic regression:
	- take numbers turn them between 0-1
	- logistic = linear + sigmoid to get probability
	- why not MSE? => non-convex shape(many local minima) => we wanna reach global minima.![img](<./media/Pasted image 20251201205516.png>) => why? cuz we used sigmoid(exponential func) => cancel exp using log in loss func!
	- loss = (1-y^)log + y log(y^) => نصين المعادلة هيديني convex shape
	- بطيّر جزء من المعادلة حسب انا في صفر ولا واحد class => رجعنا لينيار تاني
	- كذا كلاس بقا: 
		- 1 v 1: خط يفرق بين كلاسين ويسيب التالت وهكذا مع كل اتنين لوحدهم
		- 1 v R:  ![img](<./media/Pasted image 20251201210749.png>)
		- O v R: multiple models functioning as binary for each 2 classes
- polynomial regression: 
- loss function(while trainning) - metrices(after trainning) => loss func can be metrices
	- regression: 
		- MAE(robust against outliers, easy t interpret) - (big error - ignore) - (non-convex shape) => sub gradient
		- MSE(penality for big error) - (convex) - (outliers sensitive) - (not interpretable) 
		- RMSE(interpretable than mse) - (very sensitive t outliers) - (care bout big error => avg sqr)
		- الموديل فاهم قد إيه من الداتا أو فارينس الداتا (R^2
		- أي عامود زودته = فارينس جديد اتعلمه (حتى ولو كان اصفار او وحايد بس)
		- بيعاقب الموديل لو زود r^2 مع زيادة العواميد اكا الفيتشرز => بينالتي (مقياس | ميتريك)
	- classification:
		- confusion matrix => acc, precession, recall 
		- ![img](<./media/Pasted image 20251201215123.png>)
		- positive = الحاجة اللي أنا مهتم بيها سواء السبام او لا
		- الاكيورسي بتساوي الصح \ التوتال بتاع الصح => عندي موسيبه فيه حاجات همة عملها سبام
		- البيرسيجن بيهتم باللي أنا عملته سبام وهو مش سبام (كام واحد فعلا سبام؟)
		- ريكول السبام اللي جالي كام واحد عملته سبام فعلا؟
		- f1 score => perc + recall
		- f-beta => u decide which u interested in
- decision tree: subset data t classify them => depending on entropy(معامل العشوائية- بقلله) + info gain(عكس الانتروبي- بزوده) 
- impurity(geni index - entropy) => very strong but easy t overfit
- pre-prune => max depth, min sample, max sample
- post-pruning => pruning, randomly cut pieces then see accuracy effect
- مبني عليه ال ensemble method=> موديلز ضعيفة سوا = موديل قوي (stacking, boosting, bagging, cascading)
- haar cascading => ensemble model cascading! CV 2000s
DL:
- i give him problem + solution => it gives me algo
- part of ml
- works with any type of data
- works with large amounts of data => better accuracy
- need large computational power
- specific in complex patterns

## Decision tree
- probabilistic models:
	- الموجيلز المعتمدة على الماث بتتأثر بال nulls, features scaling, dups لأنها بتاخد من الداتا ارقام تضربها في ال weights

- dt:
	- probabilistic
	- supervised algo, classification+regression
- entropy: الداتا متداخلة في بعضها بنسبة قد إيه؟ => نقلل الانتروبي
- gini-index: used as default for entrpoy; used for probability.
- overfitting:
	- pruning technique => regularization
	- pre-pruning: قبل ما اعمل ترين: بحدد شوية كريتيريا يقف عندها(early stopping -> max depth || min-sample-spilt -> بحددله عدد معين || min-sample/leaf -> القرار بتاع ال ليف متاخد بناء على كام بوينت؟ أقل حاجة كذا وإلا تتلغي السبليت دي || min-impurity-decrease: بشوف الامبيوريتي قلت قد إيه وأقسم) => i got many many hyperparameters to choose.
	- post-pruning: (cost-complexity: بشوف الكوست بتاع كل فرع => كل ما كان أكبر بمسح الفرع دا || min-description-leng: بيحاول يوصل لأقل فروع توصف الداتا) => best as i see all the data splits, yet it's computationally costing, so most ppl use pre-pruning.
- regression-tree: مع كل تقسيمة خط جديد![img](<./media/Pasted image 20251206094238.png>)
- PROS:
	- interpretability: سهلة الفهم\ليه القرار دا اتاخد؟
	- ensemble usage: اهم حاجة في الماشين ليرنينج
- CONS:
	- overfitting: سهل جدا ت over-fit بعيدا عن ال pruning
	- performance with many features => ضياع(بحث)
- استخدامه: أي مجال محتاج تفسير للقرار بتاعي


## Ensemble methods
- مجموعة موديلز شغالين سوا => اكيوريسي أعلى، اوفر فيت أقل
- diversity: come-over weak points in some models
- majority vote: stops noise
- types:
	- bagging: parallel
		- boot-strap aggregation, bags of data randomly(with replacement) => train on (rows: create dataset, then cols: to min variance)كل سبليت بوريله فيتشرز معينة من الداتا مش كلهم، لأن كل تري بتتبني لوحدها، لو معملتش كدا يبقا عطيت كل موديل كل الداتا 
		- out of bag: rows won't be taken
		- random feature/split: no identical trees, low variance
	- boosting: sequential
			- ada-boost => gradient boost => XG-Boost: parallel-training, no overfit, tree-pruning auto(max-post-production), best in non-linear data, state-of-art, PROBLEM: HYPERPARAMETER
			- light-GBM(gradient-boost model): faster, bigger data safely, ranking/recommendation sys
			- Cat-boost(categorical): no encoding needed, cat problems, less bias, e-commerce
		- كل موديل بيشتغل على أخطاء اللي قبله => بدي weight أكبر للأخطاء بتاع الموديل إللي قبلي => بقوله ركز على البوينتس دي صنفها صح
		- weighted vote: الشجرة ال بتغلط كتير بديها وزن أقل
		- ![img](<./media/Pasted image 20251206101903.png>)
	- stacking:  
		- weak learner: learns on meta-data of models! 
		- ![img](<./media/Pasted image 20251206102536.png>)
		- بدي وزن لكل موديل بنائ على القرار الاخير اللي اخدته منهم وأشوف مين أصح أزود الوزن بتاعه
		- hard-voting: final vote, soft-voting: prob vote


## Un-Supervised
## Clustering
- k-means
	- affected by: # classes, تداخلهم وتباعدهم, scaling sensitive, outliers sensitive, 
- DB-Scan: density-based spatial cluster application with noise => deals with noisy data: بيشغل بمفهوم هندسي(بعمل radius(epsilon) لكل نقطة، لو حواليها 3 نقط عالأقل = core point يعني داتا حقيقية)![img](<./media/Pasted image 20251206114505.png>) لو نقطة حواليها عدد نقط مش كفاية = border بحدد لو نويز او لا => لو واحدة من اللي حواليها core point, لو لا يبقا اكيد نويز
- hierarchal clustering
- association rule
- gaussian mixture model

كفاءة ال cluster: بيحسب المسافة بين نقط الكلاستر الواحد وبعدها المسافة بين كل الكلسترز -> سوليوت سكور
## Dimensionality Reduction
- PCA: doesn't work with non-linear
- t-SNE
- U-Map

feature selection: choose features depending on criteria
dim-reduction: compress values