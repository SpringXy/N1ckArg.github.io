<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
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
  <input type="text" id="codeInput" placeholder="•••">
  <button onclick="checkCode()">Submit</button>
  <div id="message"></div>

  <script>
    const secrets = {
      "d3mon1x": "No matter how much I love you, sadly this ain't the answer, I'm sorry sweetheart. </3 TnT",
      "styxsi": "The person who gave me the code to work on it, THANKS YOU STYXS <3 ",
      "stream": "https://www.twitch.tv/springxy",
      "nick": "He's not here.",
      "valie": "Don't you DARE use that code again, a**hole.",
      "springxy": "Nice Try",
      "gorefield": "PERDONANOS, TE RETRASAMOS 2 AÑOS",
      "thunder": "Thanks for everything...I love you",
      "savory": "I LOVE HIM SO MUCH AAA",
      "error": "N1c3 Tr4, 4n0m4ly",
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
      "dream" : "P dpzo aoha lclyfaopun P mpnoa mvy...dhz uva mvy uvaopun...huk puzalhk aopunz hjabhssf ohwwlulk...zv wslhzl...kvu'a sla aopz il hdhf..."
    };

    function checkCode() {
      const input = document.getElementById("codeInput").value.trim().toLowerCase();
      const messageDiv = document.getElementById("message");
      const matchedSecret = secrets[input];

      messageDiv.textContent = matchedSecret || "Invalid Password. Please try again.";
    }
  </script>

</body>
</html>
