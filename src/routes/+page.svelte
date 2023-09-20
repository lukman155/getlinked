<script>
	import Navbar from "./Navbar.svelte";
</script>


<main class="container">
  <Navbar />
  <section class="section-wrapper">
  <div class="headline-wrapper">
    <h2 class='headline'>Igniting a Revolution in HR Innovation</h2>
    <svg xmlns="http://www.w3.org/2000/svg" width="117" height="11" viewBox="0 0 117 11" fill="none">
      <path d="M1 9C20.2424 3.71764 70.7273 -3.67768 116 9" stroke="#FF26B9" stroke-width="3"/>
    </svg>    
  </div>
  <div class="title">      
    
    <h1><span>
      <img class='bulb-float' src="creative.png" alt="creative-emoji">
    </span>getlinked Tech<br>
      Hackathon <span style="color:#D434FE;">1.0</span>
      <span>
        <img class='' src="chain.png" alt="star">
        <img class='' src="Bang.png" alt="star">
        
      </span>
      </h1>
  </div>
  <img class='stars hero1'src="star-group-1.png" alt="star">
  <p>
    Participate in getlinked tech Hackathon 
2023 stand a chance to win a Big prize
  </p>

  <button class='register-button'>Register</button>

  <p class="countdown">00<span>H</span> 00<span>M</span>   00<span>S</span></p>
</section>
</main>

<style>

  .countdown {
    margin-top: 14.16px;
    color: #FFF;
    font-family: Unica One;
    font-size: 48px;
    font-style: normal;
    font-weight: 400;
    line-height: 133%; /* 63.84px */
  }

  .countdown > span {
    color: #FFF;
    font-family: Montserrat;
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 133%; /* 18.62px */
  }

  .register-button {
    margin-top: 24px;
    color:white;
    padding: 15px 46px;
    border-radius: 4px;
    background: linear-gradient(270deg, #903AFF 0%, #D434FE 56.42%, #FF26B9 99.99%, #FE34B9 100%);
  }
  p {
    color: #FFF;
    text-align: center;
    font-family: Montserrat;
    font-size: 13px;
    font-style: normal;
    font-weight: 400;
    line-height: 166%; 
    max-width: 264px;
    margin: 0;
  }

.bulb-float {
  position: absolute;
  top: -14px;
  left: 232px;

}

.stars.hero1 {
  display: block; /* Initially visible */
  opacity: 0; /* Initially fully transparent */
  animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
}

/* Define animation keyframes */
@keyframes fadeInOut {
  0% {
    opacity: 0; /* Start fully transparent */
  }
  50% {
    opacity: 1; /* Middle of animation, fully visible */
  }
  100% {
    opacity: 0; /* End of animation, fully transparent */
  }
}

  h1 {
    font-family: 'ClashDisplay-Bold';
    margin-top: 44px;
    font-size: 32px;
    font-weight: 700;
    line-height: 39px;
    letter-spacing: 0em;
    text-align: center;
    position: relative;
    margin-bottom: 9px;
  }

  .stars {
    position: absolute;
    top: 152px;
    left: 120px;
  }
    .container {
    min-width: 390px;
    background: url(Purple-Lens-Flare-PNG.png) no-repeat;
    background-blend-mode: lighten;
    
  }

  .section-wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .headline-wrapper {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }

  .headline {
    margin-top: 24px;
    color: #FFF;
    font-family: Montserrat;
    font-size: 16px;
    font-style: italic;
    font-weight: 700;
    line-height: normal;
    margin-bottom: 7px;
  }

  


</style>