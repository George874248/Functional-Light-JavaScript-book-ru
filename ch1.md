# Functional-Light JavaScript
# Глава 1: Почему Функциональное Программирование?

> Functional programmer: (noun) One who names variables "x", names functions "f", and names code patterns "zygohistomorphic prepromorphism"
>
> James Iry ‏@jamesiry 5/13/15
>
> https://twitter.com/jamesiry/status/598547781515485184

Функциональное программирование (FP) как бы то ни было не является новой концепцией. Оно существовало с самого начала истории  программирования. Однако -- я не уверен что сказать это будет справедливо, но! -- FP не выглядело как основной концепцией разработчиков до последний пары лет. Я думаю, что FP больше относится к ученой сфере.

Но все меняется. Огромный интерес растет вокруг FP, не только на уровне языка, но даже в библиотеках и фреимверках. Вы заинтересовано читаете, потому что вы наконец поняли, что вы больше не в силах игнорировать FP. Или, может быть, вы похожи на меня, и вы пытались многому научиться в FP, но изо всех сил пытались пробраться через все термины или математические обозначения.

Какой бы ни была причина, добро пожаловать на вечеринку

## Уверенность

Я имею очень простую предпосылку которая лежит в основе всего что я делаю в качестве учителя разработки (на JavaScript): код, которому вы не доверяете, это код который вы не понимаете. Кроме того, если вы не доверяете или не понимаете свой код, тогда у вас не может быть никакой уверенности, что вы используете код по назначению. Вы можете запустить программу и скрестить пальцы

Что я понимаю под доверием? Я имею ввиду, что при просмотре кусков кода, вы должны точно знать что они делают, а не полагаться на то, как они казалось бы должны работать. Возможно, чаще, чем мы должны, мы склонны полагаться на проверку правильности нашей программы за счет запуска наборов тестов. Я не говорю что это плохо. Но я думаю, что мы должны стремиться к пониманию кода на столько, чтобы быть уверенными что все тесты пройдут до их запуска.

Я считаю, что методы, составляющие основу FP, сделаны таким образом, 
I believe the techniques that form the foundation of FP are designed from the mindset of having far more confidence over our programs just by reading them. Someone who understands FP, and who diligently uses it in their programs, will write code that they can read and verify, by the principles they have already proven to be true, that the program will do what they want.

Я надеюсь, что вы начнете проявлять больше уверенности в написании кода, и что эти принципы программирования функционального света начнут ваше путешествие в этом направлении.

## Связь

Почему функциональное программирование важно? Чтобы ответить на это, нам нужно сделать больший шаг назад и поговорить о том, почему важно само программирование.

Возможно вы удивитесь, но я не считаю, что код - это прежде всего набор инструкций для компьютера. На самом деле, я думаю, что тот факт, что код инструктирует компьютер, - это почти счастливая случайность.

Я очень глубоко убежден, что гораздо более важная роль кода - это средство общения с другими людьми.

Вероятно, по опыту вы знаете, что ужасно много времени, потраченное на «написание кода», фактически потрачено на чтение существующего кода. Очень немногие из нас настолько привилегированы, что тратят всю или большую часть нашего времени, внедряя свой код, и никогда не работают уже с написанным ранее.

Знаете ли вы, что люди изучающие эту тему, утверждают, что 70% процентов времени поддержки кода это его изучение? Я нахожу это шокирующим. 70%. Неудивительно, что средний показатель написания строк кода программистом в день, составляет около 5. Мы проводим другие 7 часов и 30 минут дня, просто читая код, чтобы выяснить, где эти 5 строк должны быть!

Я считаю, что мы должны хорошо сосредаточиться! по большей части на читабельности нашего кода. И кстати, читабельность, это не про количество символов. На самом деле на читаемость влияет ознокомление (да, это тоже будет изучено)

Итак, если мы собираемся потратить больше времени на создание кода, который будет более читабельным и понятным, FP окажется действительно удобным шаблоном для этих целей. Принципы FP хорошо известны, глубоко изучены и проверены, и доказуемо поддаются проверке.

Если мы будем использовать принципы FP, я считаю, что мы создадим код, с которым легче работать. Как только мы узнаем эти принципы, они будут узнаваемы и знакомы в коде, а это означает, что мы потратим меньше времени на то, чтобы выяснить, что делает каждый кусок кода. Наше внимание будет сосредоточено на том, как собираются созданные части lego, а не на том, что означают эти части lego.

FP (по крайней мере, без учета всей терминологии) является одним из наиболее эффективных инструментов для написания читаемого кода. Вот почему это так важно.

### Кривая читабельности

Это действительно важно, я воспользуюсь моментом чтобы показать явление, которое на протяжение многих лет меня расстраивало, и особенно остро стояло при написании этой книги.

Также я думаю, что это, вероятно, то, с чем многие разработчики сталкиваются. Вы, дорогой читатель, можете просто оказаться в той же лодке, читая это. Соберитесь; Если вы выдержите, кривая вернется.

<p align="center">
	<img src="fig17.png" width="600">
</p>

Мы рассмотрим это более подробно в следующей главе, но императивный код - это код, который вы, вероятно, уже пишете, например, инструкции `if` и` for`-циклы. Он ориентирован на то, чтобы точно проинструктировать компьютер о том, что нужно сделать. Декларативный код и, кроме того, тот код, который мы будем стремиться научиться писать, придерживаясь принципов FP, - это код, который больше ориентирован на описание того, какой результат

Декларативный код и вдобавок тот код, к которому мы будем стремиться, придерживаясь принципов FP, - это код, который больше ориентирован на описание результата.

Позвольте рассказать о неприятной вещи, с которой я пытался мириться, в время работы над книгой: потребуется много усилий, а порой и большего количество кода, чтобы улучшить читаемость вашего кода и минимизировать или устранить большинство мест, где вы могли бы наделать ошибки.

Если вы надеетесь, что ваш рефакторинг кода в код FP немедленно сделает ваш код более изящным, элегантным, умным и лаконичным, это просто нереалистичное ожидание - по крайней мере, не поначалу.

FP совершенно другой подход к тому, как должен быть структурирован код чтобы сделать информацию более очевидной, и чтобы помочь читателю вас понять. Этот шаг весьма полезен, но это может затянуться, т.к. код, который вы получите в конечном итоге, не будет казаться более читаемым, пока вы не потратите большое количество времени, чтобы приучить себя к FP

Так же, мой опыт говорит о том, что требуется около полутора десятков попыток превратить фрагмент императивного кода в более декларативный FP, прежде чем я получу то, что достаточно ясно для меня. Для меня, писать функциональный код, это больше процесс, чем двоичный перевод из одной парадигмы в другую.

Я также применяю метод «прочитаю его позже» для каждого фрагмента кода FP, который я пишу. Я пишу это, затем оставляю код один на несколько часов или один день, затем возвращаюсь и стараюсь читать его на свежую голову. Обычно бывает путанница, поэтому я еще раз его разбираю.

Функциональное программирование не является для меня как - достижение единственного элегантного удара кисти на холсте художника, который оставляет аудиторию в страхе. Скорее, это кропотливый, подробный, иногда предательский хак через сорняки забытого поля.

Я не отговариваю вас. Я действительно хочу чтобы вы прошли через это. Я рад тому, что у меня есть. Я могу наблюдать, как кривая читаемости стремится вверх. Это стоило того. Я верю, что это будет и у вас.

## Взятие

Мы собираемся приблизиться к FP с нуля и раскрыть основные основополагающие принципы, которые, как я полагаю, официальные FPers признают, и которые являются основой для всего, что они делают. Но по большей части мы останемся на расстоянии вытянутой руки от большей части запугивающей терминологии или математической нотации, которая легко может отпугнуть начинающих.

Я считаю более важным знать принцип и механизм работы устройства, чем знать его название. Это не отменяет важность общей терминологии - она несомненно облегчает общение между опытными профессионалами. Но я нахожу это необязательным для начинающего

Поэтому я надеюсь, что эта книга будет направлена на базовые концепции и меньше на причудливую терминологию. Это не говорит о том что ее не будет; она определенна будет. Но не увлекайтесь. Вдумайтесь в их суть. Вот о чем будет эта книга.

he less formal practice herein "Functional-Light Programming" because I think where the formalism of true FP suffers is that it can be quite overwhelming if you're not already accustomed to formal thought. Я не гадаю; Это мой опыт. Даже после обучения FP и написания этой книги, я все же могу сказать, что формализм терминов и обозначений в FP очень, очень сложно для меня. Я пытался и пытался, и похоже, что я не могу с этим справиться.

Я знаю много программистов функциоального стиля которые верят, что формализм помогает им в изучении. Но я думаю, что там есть утес, где это только начинает походить на правду когда вы достигнете определенного комфорта с формализмом. Если вы распологаете основами математики или имеете опыт в CS (Mathematics for Computer Science), это может облегчить вам задачу. Но некоторые из нас этого не делают, и как бы мы ни старались, формализм продолжает мешать.


Таким образом, в этой книге представлены концепции, на которых я полагаю, основано FP, но приходит к ним, давая вам толчок на скалу, не бросает вас прямо на нее, а дает понять как на нее попасть.

## YAGNI - "You Ain't Gonna Need It" (Вам это не понадобится)

Если вы давно в программировании, скорее всего, вы уже слышали фразу "YAGNI": "You Ain't Gonna Need It"(Вам это не понадобится). Этот принцип в основном исходит из экстремального программирования и подчеркивает высокий риск и стоимость написания функции до ее необходимости.

Иногда мы предполагаем, что нам понадобится функция в будущем, создайте ее сейчас, в надежде, что это будет так же просто как и в создании других вещей, но потом мы понимаем что ошибались, и функция вовсе не нужна, или же она должна быть немного другой. В других случаях мы бываем правы, но создаем функцию слишком рано, и всасываем время из функций, которые действительно необходимы сейчас; Мы берем альтернативные издержки в разбавлении нашей энергии.

 Other times we guess right, but build a feature too early, and suck up time from the features that are genuinely needed now; we incur an opportunity cost in diluting our energy.

YAGNI challenges us to remember: even if it's counter intuitive in a situation, we often should postpone building something until it's presently needed. We tend to exaggerate our mental estimates of the future refactoring cost of adding it later when it is needed. Odds are, it won't be as hard to do later as we might assume.

As it applies to functional programming, I would give this admonition: there will be plenty of interesting and compelling patterns discussed in this text, but just because you find some pattern exciting to apply, it may not necessarily be appropriate to do so in a given part of your code.

This is where I will differ from many more formal FPers: just because you *can* FP something doesn't mean you *should* FP it. Moreover, there are many ways to slice a problem, and even though you may have learned a more sophisticated approach that is more "future-proof" to maintenance and extensibility, a simpler FP pattern might be more than sufficient in that spot.

Generally, I'd recommend to seek balance in what you code, and to be conservative in your application of FP concepts as you get the hang of things. Default to the YAGNI principle in deciding if a certain pattern or abstraction will help that part of the code be more readable or if it's just introducing more clever sophistication that isn't (yet) warranted.

> Reminder, any extensibility point that’s never used isn’t just wasted effort, it’s likely to also get in your way as well
>
> Jeremy D. Miller @jeremydmiller 2/20/15
>
> https://twitter.com/jeremydmiller/status/568797862441586688

Remember, every single line of code you write has a reader cost associated with it. That reader may be another team member, or even your future self. Neither of those readers will be impressed with overly clever unnecessary sophistication to show off your FP agility.

The best code is the code that is most readable in the future because it strikes exactly the right balance between what it can/should be (idealism) and what it must be (pragmatism).

## Resources

I have drawn on a great many different resources to be able to compose this text. I believe you too may benefit from them, so I wanted to take a moment to point them out.

### Books

Some FP/JavaScript books that you should definitely read:

* [Professor Frisby's Mostly Adequate Guide to Functional Programming](https://drboolean.gitbooks.io/mostly-adequate-guide/content/ch1.html) by [Brian Lonsdorf](https://twitter.com/drboolean)
* [JavaScript Allongé](https://leanpub.com/javascript-allonge) by [Reg Braithwaite](https://twitter.com/raganwald)
* [Functional JavaScript](http://shop.oreilly.com/product/0636920028857.do) by [Michael Fogus](https://twitter.com/fogus)

### Blogs/Sites

Some other authors and content you should check out:

* [Fun Fun Function Videos](https://www.youtube.com/watch?v=BMUiFMZr7vk) by [Mattias P Johansson](https://twitter.com/mpjme)
* [Awesome FP JS](https://github.com/stoeffel/awesome-fp-js)
* [Kris Jenkins](http://blog.jenkster.com/2015/12/what-is-functional-programming.html)
* [Eric Elliott](https://medium.com/@_ericelliott)
* [James A Forbes](https://james-forbes.com/)
* [James Longster](https://github.com/jlongster)
* [André Staltz](http://staltz.com/)
* [Functional Programming Jargon](https://github.com/hemanth/functional-programming-jargon#functional-programming-jargon)
* [Functional Programming Exercises](https://github.com/InceptionCode/Functional-Programming-Exercises)

### Libraries

The code snippets in this book do not use libraries. Each operation that we discover, we'll derive how to implement it in standalone, plain ol' JavaScript. However, as you begin to build more of your real code with FP, you'll quickly want a library to provide optimized and highly reliable versions of these commonly accepted utilities.

By the way, you'll want to make sure you check the documentation for the library functions you use to make sure you know how they work. There will be a lot of similarities in many of them to the code we build on in this text, but there will undoubtedly be some differences, even between popular libraries.

Here are a few popular FP libraries for JavaScript that are a great place to start your exploration with:

* [Ramda](http://ramdajs.com)
* [lodash/fp](https://github.com/lodash/lodash/wiki/FP-Guide)
* [functional.js](http://functionaljs.com/)
* [Immutable.js](https://github.com/facebook/immutable-js)

Appendix C illustrates some of these libraries using various examples from the text.

## Summary

This is Functional-Light JavaScript. The goal is to learn to communicate with our code but not suffocate under mountains of notation or terminology to get there. I hope this book jumpstarts your journey!
