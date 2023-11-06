

![Star Badge](https://img.shields.io/static/v1?label=%F0%9F%8C%9F&message=If%20Useful&style=style=flat&color=BC4E99)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)
[![View Repositories](https://img.shields.io/badge/View-My_Repositories-blue?logo=GitHub)](https://github.com/yaswanthteja?tab=repositories)
[![View My Profile](https://img.shields.io/badge/View-My_Profile-green?logo=GitHub)](https://github.com/yaswanthteja)


# Typing-speed-test
typing speed test is build on the javascript, css and html

Typing speed test is a game where you can check your typing speed like WPM (Word Per Minute), CPM (Character Per Minute), Accuracy, etc. In my Typing Speed Test Game, the max time for typing is 60 seconds. Once you start typing, you’ll see your time, mistakes, WPM, and CPM at the bottom.
You can also erase your incorrect characters or go backward by pressing the backspace key of your keyboard. Once you have typed all characters or the time is completed, you can click on the try again button to reset the result and load a new paragraph.

To create this Typing Speed Test Game in JavaScript. First, you need to create four Files: HTML, CSS & JavaScript Files. After creating these files just paste the following codes into your file. You can also download the source code files of this Typing Speed Test Game from [Github](https://github.com/yaswanthteja/Typing-speed-test)

# [LIVE DEMO](https://typing-speed-test-swart.vercel.app/)

First, create an HTML file with the name of index.html and paste the given codes in your HTML file. Remember, you’ve to create a file with .html extension.

```
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">  
    <title>Typing Speed Test </title>
    <link rel="stylesheet" href="style.css">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
    <div class="wrapper">
      <input type="text" class="input-field">
      <div class="content-box">
        <div class="typing-text">
          <p></p>
        </div>
        <div class="content">
          <ul class="result-details">
            <li class="time">
              <p>Time Left:</p>
              <span><b>60</b>s</span>
            </li>
            <li class="mistake">
              <p>Mistakes:</p>
              <span>0</span>
            </li>
            <li class="wpm">
              <p>WPM:</p>
              <span>0</span>
            </li>
            <li class="cpm">
              <p>CPM:</p>
              <span>0</span>
            </li>
          </ul>
          <button>Try Again</button>
        </div>
      </div>
    </div>

    <script src="js/paragraphs.js"></script>
    <script src="js/script.js"></script>
  
  </body>
</html>
```
Second, create a CSS file with the name of style.css and paste the given codes in your CSS file. Remember, you’ve to create a file with .css extension.
```
/* Import Google Font - Poppins */
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}
body{
  display: flex;
  padding: 0 10px;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background: #17A2B8;
}
::selection{
  color: #fff;
  background: #17A2B8;
}
.wrapper{
  width: 770px;
  padding: 35px;
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 10px 15px rgba(0,0,0,0.05);
}
.wrapper .input-field{
  opacity: 0;
  z-index: -999;
  position: absolute;
}
.wrapper .content-box{
  padding: 13px 20px 0;
  border-radius: 10px;
  border: 1px solid #bfbfbf;
}
.content-box .typing-text{
  overflow: hidden;
  max-height: 256px;
}
.typing-text::-webkit-scrollbar{
  width: 0;
}
.typing-text p{
  font-size: 21px;
  text-align: justify;
  letter-spacing: 1px;
  word-break: break-all;
}
.typing-text p span{
  position: relative;
}
.typing-text p span.correct{
  color: #56964f;
}
.typing-text p span.incorrect{
  color: #cb3439;
  outline: 1px solid #fff;
  background: #ffc0cb;
  border-radius: 4px;
}
.typing-text p span.active{
  color: #17A2B8;
}
.typing-text p span.active::before{
  position: absolute;
  content: "";
  height: 2px;
  width: 100%;
  bottom: 0;
  left: 0;
  opacity: 0;
  border-radius: 5px;
  background: #17A2B8;
  animation: blink 1s ease-in-out infinite;
}
@keyframes blink{
  50%{ 
    opacity: 1; 
  }
}
.content-box .content{
  margin-top: 17px;
  display: flex;
  padding: 12px 0;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  border-top: 1px solid #bfbfbf;
}
.content button{
  outline: none;
  border: none;
  width: 105px;
  color: #fff;
  padding: 8px 0;
  font-size: 16px;
  cursor: pointer;
  border-radius: 5px;
  background: #17A2B8;
  transition: transform 0.3s ease;
}
.content button:active{
  transform: scale(0.97);
}
.content .result-details{
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  width: calc(100% - 140px);
  justify-content: space-between;
}
.result-details li{
  display: flex;
  height: 20px;
  list-style: none;
  position: relative;
  align-items: center;
}
.result-details li:not(:first-child){
  padding-left: 22px;
  border-left: 1px solid #bfbfbf;
}
.result-details li p{
  font-size: 19px;
}
.result-details li span{
  display: block;
  font-size: 20px;
  margin-left: 10px;
}
li span b{
  font-weight: 500;
}
li:not(:first-child) span{
  font-weight: 500;
}
@media (max-width: 745px) {
  .wrapper{
    padding: 20px;
  }
  .content-box .content{
    padding: 20px 0;
  }
  .content-box .typing-text{
    max-height: 100%;
  }
  .typing-text p{
    font-size: 19px;
    text-align: left;
  }
  .content button{
    width: 100%;
    font-size: 15px;
    padding: 10px 0;
    margin-top: 20px;
  }
  .content .result-details{
    width: 100%;
  }
  .result-details li:not(:first-child){
    border-left: 0;
    padding: 0;
  }
  .result-details li p, 
  .result-details li span{
    font-size: 17px;
  }
}
@media (max-width: 518px) {
  .wrapper .content-box{
    padding: 10px 15px 0;
  }
  .typing-text p{
    font-size: 18px;
  }
  .result-details li{
    margin-bottom: 10px;
  }
  .content button{
    margin-top: 10px;
  }
}
```
Third, create a folder with the js name and then create two javascript files (paragraphs.js, script.js) files inside this folder. Paste the given codes inside the paragraphs.js file. These are the paragraphs that are shown randomly as typing text. You can add more paragraphs in the array to show more paragraphs on the typing game.
```
const paragraphs = [
    "Authors often misinterpret the lettuce as a folklore rabbi, when in actuality it feels more like an uncursed bacon. Pursued distances show us how mother-in-laws can be charleses. Authors often misinterpret the lion as a cormous science, when in actuality it feels more like a leprous lasagna. Recent controversy aside, their band was, in this moment, a racemed suit. The clutch of a joke becomes a togaed chair. The first pickled chess is.",
    "In modern times the first scrawny kitten is, in its own way, an input. An ostrich is the beginner of a roast. An appressed exhaust is a gun of the mind. A recorder is a grade from the right perspective. A hygienic is the cowbell of a skin. Few can name a dun brazil that isn't a highbrow playroom. The unwished beast comes from a thorny oxygen. An insured advantage's respect comes with it the thought that the lucid specialist is a fix.",
    "In ancient times the legs could be said to resemble stroppy vegetables. We can assume that any instance of a centimeter can be construed as an enate paste. One cannot separate pairs from astute managers. Those americas are nothing more than fish. If this was somewhat unclear, authors often misinterpret the gosling as an unfelt banjo, when in actuality it feels more like a professed galley. A bow of the squirrel is assumed.",
    "What we don't know for sure is whether or not a pig of the coast is assumed to be a hardback pilot. The literature would have us believe that a dusky clave is not but an objective. Few can name a limbate leo that isn't a sunlit silver. The bow is a mitten. However, the drawer is a bay. If this was somewhat unclear, few can name a paunchy blue that isn't a conoid bow. The undrunk railway reveals itself as a downstage bamboo to those who look.",
    "Their politician was, in this moment, a notour paperback. The first armless grouse is, in its own way, a gear. The coat is a wash. However, a cake is the llama of a caravan. Snakelike armies show us how playgrounds can be viscoses. Framed in a different way, they were lost without the fatal dogsled that composed their waitress. Far from the truth, the cockney freezer reveals itself as a wiggly tornado to those who look. The first hawklike sack.",
    "An aunt is a bassoon from the right perspective. As far as we can estimate, some posit the melic myanmar to be less than kutcha. One cannot separate foods from blowzy bows. The scampish closet reveals itself as a sclerous llama to those who look. A hip is the skirt of a peak. Some hempy laundries are thought of simply as orchids. A gum is a trumpet from the right perspective. A freebie flight is a wrench of the mind. Some posit the croupy.",
    "A baby is a shingle from the right perspective. Before defenses, collars were only operations. Bails are gleesome relatives. An alloy is a streetcar's debt. A fighter of the scarecrow is assumed to be a leisured laundry. A stamp can hardly be considered a peddling payment without also being a crocodile. A skill is a meteorology's fan. Their scent was, in this moment, a hidden feeling. The competitor of a bacon becomes a boxlike cougar.",
    "A broadband jam is a network of the mind. One cannot separate chickens from glowing periods. A production is a faucet from the right perspective. The lines could be said to resemble zincoid females. A deborah is a tractor's whale. Cod are elite japans. Some posit the wiglike norwegian to be less than plashy. A pennoned windchime's burst comes with it the thought that the printed trombone is a supply. Relations are restless tests.",
    "In recent years, some teeming herons are thought of simply as numbers. Nowhere is it disputed that an unlaid fur is a marble of the mind. Far from the truth, few can name a glossy lier that isn't an ingrate bone. The chicken is a giraffe. They were lost without the abscessed leek that composed their fowl. An interviewer is a tussal bomb. Vanward maracas show us how scarfs can be doubts. Few can name an unguled punch that isn't pig.",
    "A cough is a talk from the right perspective. A designed tractor's tray comes with it the thought that the snuffly flax is a rainbow. Their health was, in this moment, an earthy passbook. This could be, or perhaps the swordfishes could be said to resemble healthy sessions. A capricorn is a helium from the right perspective. However, a sled is a mailman's tennis. The competitor of an alarm becomes a toeless raincoat. Their twist was, in this moment.",
    "Authors often misinterpret the flag as a wayless trigonometry, when in actuality it feels more like a bousy gold. Few can name a jasp oven that isn't a stutter grape. They were lost without the huffy religion that composed their booklet. Those waves are nothing more than pedestrians. Few can name a quartered semicolon that isn't a rounding scooter. Though we assume the latter, the literature would have us believe.",
    "This could be, or perhaps few can name a pasteboard quiver that isn't a brittle alligator. A swordfish is a death's numeric. Authors often misinterpret the mist as a swelling asphalt, when in actuality it feels more like a crosswise closet. Some posit the tonal brother-in-law to be less than newborn. We know that the sizes could be said to resemble sleepwalk cycles. Before seasons, supplies were only fighters. Their stew was, in this moment.",
    "The vision of an attempt becomes a lawny output. Dibbles are mis womens. The olden penalty reveals itself as a bustled field to those who look. Few can name a chalky force that isn't a primate literature. However, they were lost without the gamy screen that composed their beret. Nowhere is it disputed that a step-uncle is a factory from the right perspective. One cannot separate paints from dreary windows. What we don't know for sure is whether.",
    "A tramp is a siamese from the right perspective. We know that a flitting monkey's jaw comes with it the thought that the submersed break is a pamphlet. Their cream was, in this moment, a seedy daffodil. The nest is a visitor. Far from the truth, they were lost without the released linen that composed their step-sister. A vibraphone can hardly be considered a pardine process without also being an archaeology. The bay of a hyacinth becomes.",
    "The frosts could be said to resemble backstage chards. One cannot separate colleges from pinkish bacons. Far from the truth, the mom of a rooster becomes a chordal hydrogen. A tempo can hardly be considered a purer credit without also being a pajama. The first combined ease is, in its own way, a pantyhose. Extending this logic, the guides could be said to resemble reddest monkeies. Framed in a different way, an addle hemp is a van.",
    "Far from the truth, an ajar reminder without catamarans is truly a foundation of smarmy semicircles. An alike board without harps is truly a satin of fated pans. A hubcap sees a parent as a painful beautician. The zeitgeist contends that some intense twigs are thought of simply as effects. A cross is a poppied tune. The valanced list reveals itself as an exchanged wrist to those who look. Recent controversy aside.",
    "The hefty opinion reveals itself as a sterile peer-to-peer to those who look. This could be, or perhaps the watch of a diamond becomes a bosom baboon. In recent years, some posit the unstuffed road to be less than altern. It's an undeniable fact, really; the livelong lettuce reveals itself as an unstuffed soda to those who look. In ancient times a bit is a balance's season. The popcorn of a morning becomes a moonless beauty.",
    "If this was somewhat unclear, a friend is a fridge from the right perspective. An upset carriage is a stitch of the mind. To be more specific, a temper is a pair from the right perspective. Authors often misinterpret the liquid as a notchy baseball, when in actuality it feels more like an unbarbed angle. Though we assume the latter, the first vagrom report is, in its own way, a tower. We know that the octopus of a cd becomes an unrent dahlia.",
    "A reptant discussion's rest comes with it the thought that the condemned syrup is a wish. The drake of a wallaby becomes a sonant harp. If this was somewhat unclear, spotty children show us how technicians can be jumps. Their honey was, in this moment, an intime direction. A ship is the lion of a hate. They were lost without the croupous jeep that composed their lily. In modern times a butcher of the birth is assumed to be a spiral bean.",
    "Those cowbells are nothing more than elements. This could be, or perhaps before stockings, thoughts were only opinions. A coil of the exclamation is assumed to be a hurtless toy. A board is the cast of a religion. In ancient times the first stinko sailboat is, in its own way, an exchange. Few can name a tutti channel that isn't a footless operation. Extending this logic, an oatmeal is the rooster of a shake. Those step-sons are nothing more than matches."
];
```
Last, paste the given codes inside the script.js file and this is the main JavaScript code of this typing speed test game. If you want to increase or decrease the timer of this game then change the value of maxTime variable of this file.
```
const typingText = document.querySelector(".typing-text p"),
inpField = document.querySelector(".wrapper .input-field"),
tryAgainBtn = document.querySelector(".content button"),
timeTag = document.querySelector(".time span b"),
mistakeTag = document.querySelector(".mistake span"),
wpmTag = document.querySelector(".wpm span"),
cpmTag = document.querySelector(".cpm span");

let timer,
maxTime = 60,
timeLeft = maxTime,
charIndex = mistakes = isTyping = 0;

function loadParagraph() {
    const ranIndex = Math.floor(Math.random() * paragraphs.length);
    typingText.innerHTML = "";
    paragraphs[ranIndex].split("").forEach(char => {
        let span = `<span>${char}</span>`
        typingText.innerHTML += span;
    });
    typingText.querySelectorAll("span")[0].classList.add("active");
    document.addEventListener("keydown", () => inpField.focus());
    typingText.addEventListener("click", () => inpField.focus());
}

function initTyping() {
    let characters = typingText.querySelectorAll("span");
    let typedChar = inpField.value.split("")[charIndex];
    if(charIndex < characters.length - 1 && timeLeft > 0) {
        if(!isTyping) {
            timer = setInterval(initTimer, 1000);
            isTyping = true;
        }
        if(typedChar == null) {
            if(charIndex > 0) {
                charIndex--;
                if(characters[charIndex].classList.contains("incorrect")) {
                    mistakes--;
                }
                characters[charIndex].classList.remove("correct", "incorrect");
            }
        } else {
            if(characters[charIndex].innerText == typedChar) {
                characters[charIndex].classList.add("correct");
            } else {
                mistakes++;
                characters[charIndex].classList.add("incorrect");
            }
            charIndex++;
        }
        characters.forEach(span => span.classList.remove("active"));
        characters[charIndex].classList.add("active");

        let wpm = Math.round(((charIndex - mistakes)  / 5) / (maxTime - timeLeft) * 60);
        wpm = wpm < 0 || !wpm || wpm === Infinity ? 0 : wpm;
        
        wpmTag.innerText = wpm;
        mistakeTag.innerText = mistakes;
        cpmTag.innerText = charIndex - mistakes;
    } else {
        clearInterval(timer);
        inpField.value = "";
    }   
}

function initTimer() {
    if(timeLeft > 0) {
        timeLeft--;
        timeTag.innerText = timeLeft;
        let wpm = Math.round(((charIndex - mistakes)  / 5) / (maxTime - timeLeft) * 60);
        wpmTag.innerText = wpm;
    } else {
        clearInterval(timer);
    }
}

function resetGame() {
    loadParagraph();
    clearInterval(timer);
    timeLeft = maxTime;
    charIndex = mistakes = isTyping = 0;
    inpField.value = "";
    timeTag.innerText = timeLeft;
    wpmTag.innerText = 0;
    mistakeTag.innerText = 0;
    cpmTag.innerText = 0;
}

loadParagraph();
inpField.addEventListener("input", initTyping);
tryAgainBtn.addEventListener("click", resetGame);
```

That’s all, now you’ve successfully built a Typing Speed Test Game in HTML CSS & JavaScript. TO view the live demo click on then link below

# [LIVE DEMO](https://typing-speed-test-swart.vercel.app/)
