<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Secret Code Checker</title>
  <style>
    body {
      background-color: #111;
      color: #202af0;
      font-family: monospace;
      text-align: center;
      padding-top: 100px;
    }
    input, button {
      background-color: #000;
      color: #3c64f7;
      border: 1px solid #13076d;
      padding: 10px;
      font-size: 16px;
    }
    #message {
      margin-top: 30px;
      font-size: 20px;
      white-space: pre-wrap;
    }
  </style>
</head>
<body>

  <h1>HELLO DEAR USER</h1>
  <h2>ENTER PASSWORD</h2>
  <input type="text" id="codeInput" placeholder="•••" />
  <button onclick="checkCode()">Submit</button>
  <div id="message"></div>

  <script>
    const secrets = {
      "d3mon1x": "No matter how much I love you, sadly this ain't the answer, I'm sorry sweetheart. </3 TnT",
      "styxsi": "The person who gave me the code to work on it, THANKS YOU STYXS <3... you've been an amazing friend...I can't thanks you enough Styxs, I hope I can see you go far with your talent...",
      "stream": "https://www.twitch.tv/springxy",
      "nick": "He's not here.",
      "valie": "Don't you DARE use that code again, a**hole.",
      "springxy": "Nice Try",
      "gorefield": "PERDONANOS, TE RETRASAMOS 2 AÑOS",
      "thunder": "Thanks for everything...I love you so much...I wish I could...be able a safe place for you one day dearest...",
      "savory": "I LOVE HIM SO MUCH AAA",
      "error": "https://imgur.com/a/vr7zK2W",
      "vortex": "The real meaning behind my existence",
      "ego": "I ALREADY SAID THAT I DESPISE HIM SO MUCH.",
      "password": "Woooooooooow, that's such a nice try from you! /sarc",
      "journal": "https://docs.google.com/document/d/1pLu0g2PC_e6v18G4_CJXsWstSkNLI0eni0ESWOJmcV0/edit?usp=drivesdk",
      "femboy": "MEYUKI CUT IT OFF DAMNIT",
      "meyuki": "Man, you are one of my best friends, love you man, thanks for everything..",
      "locura": "Thanks you for everything you've done for me so far...I'll never be able to repay you...",
      "ally": "you silly aligator, thanks for being for me even with this short time, thanks you...",
      "zankow": "Even if you are the youngest person I've known, you still have all my respect...so...LOCKED AND LOADED!!!",
      "neon": "One of the most talented person's I've ever had the chance to meet",
      "skylar": "HAI YOU BOTTOM BITCH BOYYYYYYYY, love you bro, don't kill me, teehee",
      "cian": "You were one of the one's who made everything I thought impossible into possible, I love you bro, im happy to be your big brother and also be proud of you every day",
      "draco": "If it weren't for you and (INFORMATION NOT FOUND), I would have never been happy...thanks you since the bottom of my soul...",
      "twenty-nine": "The day where it should have ended",
      "23": "Haaaaaaai, Ashhhhh teehee",
      "mom": "The Devil who doesn't deserve the honor to be called like that",
      "venus": "Mi razón de poder sonreir cada dia, la razón por la cual creo de que todo es posible y de que la música es el lenguaje universal para todo, incluso el amor",
      "boreal": "One of the people that I look up to quite often!",
      "andromeda": "My silly 1/2 sibling who I love so much!! Hai Hassyyyyyyyy, you've been one of those little stars who has brought light to my life...I love you so much you little silly...",
      "kevin": "THE SILLYYYYYYYYYYYYYYYYYYYYYYYYYYYY!!!",
      "cassiopeia": "My little brother who has been one of the most amazing people I´ve known, I'll never be able to repay all the years that you've been by my side helping me, being there for me, listening to me...and caring about me...thanks you...love you bro...thanks for everything...",
      "she": "https://youtu.be/Y0XkS6rTBHE?si=rRcvk8sw9LaNRWkp",
      "sour": "Not everything in life is rainbows... ZANKOW, IF YOU DARE MAKE A F****** REFERENCE TO FLAVOR RAVE OR RAINBOW SORBET CUZ OF THIS, I'M GOING TO KI-",
      "sweet": "I wish my childhood was... ZANKOW DON'T YOU DARE",
      "dream": "P dpzo aoha lclyfaopun P mpnoa mvy...dhz uva mvy uvaopun...huk puzalhk aopunz hjabhssf ohwwlulk...zv wslhzl...kvu'a sla aopz il hdhf...",
      "trecker": "https://i.ytimg.com/vi/j9eopTtJRcE/hqdefault.jpg",
      "inner mirror": "No way!! One of my favorite mods!",
      "shads": "you've been such an amazing friend and I can't wait to get to know you better man, you are awesome",
      "deadshot": "I love you so much mf, I'm so happy to have you in my life man",
      "zeuz": "One of the most talented, determinated and passionate artist I've known, you'll get far...I'm sure of it",
      "maskiu": "thanks you for being one of my best friends...I don't think I would be were I am if it weren't for you...thanks for being one of those stars who brings light to my life",
      "love": "https://youtu.be/UTcZHzDY3LU?si=2EHDJKoKGLx-YEvE",
      "dad": "I'm so happy and lucky to be able to call you dad in this life...I hope I can do the same in the next one...",
      "jenstar": "YOU ARE AMAZING MAN, I CAN'T WISH FOR A BETTER BEST FRIEND THAN YOU, I LOVE YOU MAN AND MOON IS SO LUCKY TO HAVE YOU CUZ YOU HAVE BEEN SUCH A WONDERFUL PERSON IN MY LIFE EUUUUUUU",
      "faby": "TE QUIERO MUCHO HERMANA!!!, I'm so happy to have you as my online big sister and I'm sure that Happy artist will go far just like your talent!!!!!",
      "midnight": "thanks for being there for me when I needed you, you are amazing media noche...I mean it",
      "moonfallen": "Silence is the only what prevails...but will you sit under the stargazing night...to listen to it?",
      "grandfather": "I wish you were still here to see who I am now...I miss you dearly every day...",
      "uncle": "I miss you every day that has passed...I wish I could be able to see you once again and be able to see the man I've became...I hope you are proud of me...whenever you are",
      "nova": "I wish...you were able to see how much I've grown, no matter how hard I try, you'll always see me as your little boy...I love you so much",
      "proud": "Don't worry dad...I'll make you proud one day...maybe not today...but one day for sure!",
      "lizzy": "you lil gremlin I'm beyond proud of you every day that passes, I love you sis but please, get away from the Fazz balls...",
      "carousel": "my forever unfinished symphony",
      "spicychoco": "No Zan Zan, this story will not be about them, SOWWYYYYY",
      "bluebell": "the majestic flowers that I wish to see one day!",
      "ramware": "HEY! THIS AIN'T ABOUT THAT, COME ONNNNN!!",
      "silence": "You can't keep me quiet, I won't tremble when you try it, everything I know is that I won't go speechless",
      "drako": "Hey, I want you to know that you are one of the most amazing and sweet people I've met in my life, I'm happy to know that I have someone like you on it",
      "skullz": "I hope we can be good friends in the future...but for the love of god...GET THE FUCK OUT OF THE FUCKING GAME!!!!",
      "ashley": "You though I forgot about it? I love you so much sweetheart ",
      "addict": "Insert superskull115 picture here, please!",
      "boun": "OMG IS THE SILLYYYYY",
      "soul": "Do...I have one?...",
      "nxll": "I wish I could understand you better...",
      "existencia": "ya se que soy un error...pero por favor...¡¡SACAME ANTES DE QUE SEA TAR-..... (Communication terminated)",
      "/wavewaves": "/WAVEWAVES!!!!! ^^",
      "birthday": "is not...that important really ",
      "teto": "(If you dream something, never give up!)...huh...those words why are so familiar?...",
      "home": "Do I really have one to where belong?",
      "sun": "Azuhi, Manita, you have been nothing but such a shining star...JUST LIKE THE SUN ITSELF!!!!",
      "static": "why my memory is such a blurr?...WHY CAN'T I REMEMBER WHO I AM?!",
      "toxic": "Pero...¿la de no desinformar si te la sabes bro?...no te creas bro-",
      "jibalex": "te quiero mucho enano...nunca cambies por favor...",
      "komi": "I wish we could interact more, because of what I've seen so far you seem like a really chill and funny person!",
      "nexus": "I haven't been able to interact with you that much, but I wished I could and then be able to be your friend",
      "music box": "I just wish I could listen to this forever till my gears don't work... https://youtu.be/B2dm1PRd7O4?si=YTmstMW-OdlkDnrQ",
      "anomaly": "F1n4ll1, y0u 0p3n3d 10ur 3y3s t0 th3 4b50lut3 truth...y0u h4d y0ur fun... 1'll m4k3 5ur3 th4t n3xt t1m3...y0ur m3r3 3x15t3nc3 1s f1n4lly 0v3r.",
      "pawn": "I DONT WANNA BE CONTROLLED ANYMORE, PLEASE...I JUST WANT TO BE HAPPY",
      "devoured": "An overwhelming power that comes from above...to destroy the last pieces of humanity that I had left...",
      "doublem": "BRAWL STARS RANKEDS WHEN?! love you man",
      "november": "Some people who were born in this month they exist because of love...is not the same about me...",
      "lz": "One of the few who would have never realized...if I was replaced with something else...is not to late to apologize for what have happened...do it before you see that THING comes back...",
      "gear" : "I just wanna be myself again...Is that hard to understand?...",
      "amethyst" : "I wish I could protect myself...just like the amethyst I own does...",
      "saturn" : "sometimes...people need to be protected...but in my case I don't need protection...I wanna be the one protecting you!",
      "mercury" : "you've been nothing but sweet with me...and I hope I can repay you back everything you've done for me...",
      "crown" : "(Think no evil) ... I rather forget...to be able to forgive...",
      "ballet" : "I want my strings to be pulled no more...I want to finally rest and make the courtain fall...",
      "spanish" : "The language I wished I forgot to be able to feel normal...",
      "family" : "sometimes blood don't relate you to be people to be your family...people you care about can be your family as well!",
      "geral" : "te quiero mucho man, gracias a ti he aprendido muchas cosas...y jamas sere capaz de agradecertelo lo suficiente",
      "zorlek" : "eres un pendejo...pero te quiero mucho we...muchas gracias por los consejos y estar siempre ahi para mi",
      "agrio" : "el lider de la agrio pandillaaaaaaa, te quiero mucho we",
      "flavor rave" : "If it weren't for this mod I would have never...been happy at the end...Thanks you Duster...for everything...",
      "lava" : "Never lose hope...because the passion that ignites your heart is more powerful than you think",
      "ghost" : "why do I feel like this every day?...https://youtu.be/YlEb3L1PIco?si=5td1u03p0WcPfkjZ",
      "lilyofthevalley" : "A flower I hope to be able to gift the person I love the most",
      "reboot" : "J oir'u alyol as cenv uz vi b ixzutirmidd qfjtfx...AWFLMI, JW DZ ILLH US RPU EBEU?! XSLU T DYTX HLOE NS OS WZORYV CI L RIZMX JR APPAFIT PTQF?!, EBEU QJ WJQY HPR'E POO VYSRE WJVY E GSCPTE UX ULP SBYXW PJ WLWL...jpfedp...ipft ni rpu zox pj esjd hmhlexbcy...",
      "bestpal": "DON'T YOU GET IT?! IM YOUR BEST PAL!...AND WE'LL BE TOGETHER...FOREVER AHAHAHHAHAHAHAHAHA",
      "mafioso": "My husband",
      "osana": "an amazing friend and the best head canon voice of Rouxls!",
      "astro": "I love playing with him...I'm always like him...sleepy...",
      "blue": "Really? Did you really thought that it was going to be THAT obvious? come on, try harder!",
      "nitro": "WELCOME TO THE FUNKTRIX!",
      "carmen": "An amazing friend and such a sweet person",
      "vampire squid": "IS JUST A LIL SILLY GUY!!!!",
      "security twins": "Don't be fools...FOLLOW THE RULES!",
      "catnap": "ARTIFICIAL FACADE, FROM A FRAUD OF A GOD ALL DUE TO THE PATH THAT WE TROD",
      "b.a.d.4": "ZZSKULLS I LOVE YOU SO F****** MUCH AAAAAA",
      "flowey": "everyone hates you...but I don't...",
      "chacal": "You might be an idiot Ray...and yet...I care about you, you dumbass...",
      "deimos": "YIPPE KAH YEAH!!",
      "canvas": "CHINGA TU MADRE INK",
      "dangerous": "MY FAVORITE EPIC SONG!!!",
      "painter": "Just like you...I wanna be free as well...",
      "brainless": "Those two are my safe place...and every time I'm with them is this song playing in loop in my head...https://youtu.be/-5eAA3KnCiM?si=V0eKfMq8KOdsWcwB",
      "sin": "A la larga, mi existencia únicamente será un pecado el cual se ha de tener que afrontar tarde o temprano...",
      "loneliness": "what I don't wanna feel anymore...",
      "respect": "Am I a joke to you...right?...",
      "no": "Cut it with the lies.",
      "yes": "words tend to cut deeper than a sword...",
      "sword": "What I'll use to be free one day...",
      "valentina": "Can you...stop calling me by that name tainted with fear, tears and blood...",
      "fear": "I just want someone to stay...",
      "tears": "Will...be that day like the last time?...",
      "blood": "please...stop the pain...I don't wanna feel anything anymore...",
      "feel": "NOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORENOMORE...",
      "mars": "a nickname that made my heart go faster and also gave me a lighter way to see myself...",
      "neptune": "I don't want to be...drowned by your existence anymore...",
      "earth": "the place from where...I should have been gone...",
    };

    function checkCode() {
      const input = document.getElementById("codeInput").value.trim().toLowerCase();
      const messageDiv = document.getElementById("message");
      const matchedSecret = secrets[input];

      messageDiv.textContent = matchedSecret || "Word Unmatched. Have other idea in mind?.";
    }
  </script>

</body>
</html>
