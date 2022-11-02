# math02
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<script type="text/javascript" id="MathJax-script" async
src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>
<title>有理化</title>
<style type="text/css">
	.question{
		line-height: 10;
		margin-top: -5em;
		font-size: 75%;
	}
</style>
</head>
<body>
	<h1>確認テスト</h1>
	<p>以下の問に答えなさい</p>
<div class="question">
	<p id="q1">(1) \(\sqrt{13}-3\over \sqrt{3}\)を有理化せよ</p>
	<p id="q2">(2) \(1\over \sqrt{11}-\sqrt{5}\)を有理化せよ</p>
	<p id='q3'></p>
	<p id="q4"></p>
	<p id="q5"></p>
</div>

<script type="text/javascript">
	/* メモ
	・ランダムな数を採用する際は，条件を整理して別関数から持ってきた方がいいかもしれない．
	　→function() random_make　的な関数で数を作成したほうがいいかも
	・問題別でランダムが効くように，ボタンと関数をつないで，ボタンを押して入れ替えが出来るようにする
	  →×上手くいかなかった．原因としてhtmlを表示したタイミングしかmathjaxが反応しない可能性がある
	*/
	function randomnumber(data, data2){
		var variable = Math.floor(Math.random() * data + 1);
		//console.log(variable);
		if (Number.isInteger(Math.sqrt(variable))) {
			//console.log(Number.isInteger(Math.sqrt(variable)));
			variable += 1;
			//console.log(variable);
		}else{
			//console.log(Number.isInteger(Math.sqrt(variable)));
			//console.log(variable);
		}
		var variable2 = Math.floor(Math.random() * data2 +1);
		if (Number.isInteger(Math.sqrt(variable2))) {
			//ルートで整数になる数は１を足す
			variable2 += 1;
		}
		if (variable == variable2) {
			variable2 += 1;
		}
		if (Number.isInteger(Math.sqrt(variable2))) {
			variable2 +=1;
		}
		return [variable,variable2];
		
	}

	/*
	  title設定
	*/
	var today = new Date();
	let titlename = document.getElementsByTagName('title');
	console.log(titlename.item(0).innerHTML);
	titlename.item(0).innerHTML = today.getFullYear() + "年" + (today.getMonth()+1) +"月"+ today.getDate() + "日　神保";

	/*
	 Question1
	*/
	var q1 = document.getElementById('q1');
	console.log(q1.innerHTML);

	/*
	 Question3
	*/
	var q3 = document.getElementById('q3');
	console.log(q3.innerHTML);
	q3num = randomnumber(3,5);
	console.log(q3num[0],q3num[1]);
	q3.innerHTML = '(3) \\('+ q3num[0] + '\\sqrt{'+ q3num[1] +'}\\over \\sqrt{'+ q3num[0] +'} \\)' + '÷' +'\\(\\frac{1}{'+q3num[0]*3 +'}- 3 \\sqrt{'+q3num[0]*q3num[1]+'} \\)' +'を計算せよ';
	//q3.innerHTML = q3.innerHTML + ' \\(4 (\\sqrt{'+ q3num[0] +'}-\\sqrt{'+ q3num[1] + '})\\over '+ q3num[0] + '-' + q3num[1] +' \\)';
	
	/*
	 Question4
	*/
	var q4 = document.getElementById('q4');
	console.log(q4.innerHTML);
	q4num = randomnumber(2,7)
	q4.innerHTML = '(4) \\('+ q4num[0] + '\\sqrt{'+ q4num[1] +'}\\over \\sqrt{'+ q4num[0] +'} \\)' + '×' +'\\(\\frac{1}{'+q4num[0]*3 +'}+ 3 \\sqrt{'+q4num[0]*q4num[1]+'} \\)' +'を計算せよ';


	/*
	 Question5
	*/
	var q5 = document.getElementById('q5');
	console.log(q5.innerHTML);
	q5num = randomnumber(5,7);
	q5.innerHTML = '(5) \\('+ q5num[0] + '\\sqrt{'+ q5num[1] +'}\\over \\sqrt{'+ q5num[0] +'} \\)' + '×' +'\\(\\frac{1}{'+q5num[0]*3 +'}+ 3 \\sqrt{'+q5num[0]*q5num[1]+'}×\\frac{2}{7} \\)' +'を計算せよ';






</script>
</body>
</html>
