<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Brahma — Scroll Poem</title>
<style>
  body {
    margin: 0;
    padding: 0;
    background-color: #0d0d0d;
    color: #f2f2f2;
    font-family: "Georgia", serif;
    height: 500vh; /* allows scrolling */
  }

  .poem-container {
    position: sticky;
    top: 40%;
    transform: translateY(-50%);
    text-align: center;
    font-size: 1.8rem;
    line-height: 1.6;
    width: 80%;
    margin: auto;
  }

  .line {
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.8s ease-out;
    position: absolute;
    width: 100%;
  }

  .line.visible {
    opacity: 1;
    transform: translateY(0);
  }

  h2 {
    text-align: center;
    margin-bottom: 30px;
    font-weight: 600;
    letter-spacing: 1px;
  }
</style>
</head>
<body>

<div class="poem-container">
  <h2>Brahma — Ralph Waldo Emerson</h2>

  <div class="line">If the red slayer think he slays,</div>
  <div class="line">Or if the slain think he is slain,</div>
  <div class="line">They know not well the subtle ways</div>
  <div class="line">I keep, and pass, and turn again.</div>

  <div class="line">Far or forgot to me is near;</div>
  <div class="line">Shadow and sunlight are the same;</div>
  <div class="line">The vanished gods to me appear;</div>
  <div class="line">And one to me are shame and fame.</div>

  <div class="line">They reckon ill who leave me out;</div>
  <div class="line">When me they fly, I am the wings;</div>
  <div class="line">I am the doubter and the doubt;</div>
  <div class="line">And I the hymn the Brahmin sings.</div>

  <div class="line">The strong gods pine for my abode,</div>
  <div class="line">And pine in vain the sacred Seven,</div>
  <div class="line">But thou, meek lover of the good!</div>
  <div class="line">Find me, and turn thy back on heaven.</div>
</div>

<script>
  const lines = document.querySelectorAll('.line');
  const numLines = lines.length;

  window.addEventListener('scroll', () => {
    const scrollTop = window.scrollY;
    const maxScroll = document.body.scrollHeight - window.innerHeight;
    const scrollFraction = scrollTop / maxScroll;

    const index = Math.min(
      numLines - 1,
      Math.floor(scrollFraction * numLines * 1.2) // adjust speed
    );

    lines.forEach((line, i) => {
      line.classList.toggle('visible', i === index);
    });
  });
</script>

</body>
</html>


