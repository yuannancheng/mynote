<!-- 封面 -->



<svg xmlns="http://www.w3.org/2000/svg" id="orrery" enable-background="new 0 0 300 300" viewBox="0 0 300 300">
    <circle class="Sun" cx="150" cy="150" r="5"/>
	<g class="Mercury">
	  <circle cx="150" cy="150" r="10" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="140" cy="150" r="1.5"/>
	</g>
	<g class="Venus">
	  <circle cx="150" cy="150" r="15" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="135" cy="150" r="1.6"/>
	</g>
	<g class="Earth">
	  <circle cx="150" cy="150" r="22" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="128" cy="150" r="2"/>
	</g>
	<g class="Mars">
	  <circle cx="150" cy="150" r="30" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="120" cy="150" r="1.8"/>
	</g>
	<g class="Jupiter">
	  <circle cx="150" cy="150" r="50" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="100" cy="150" r="6"/>
	</g>
	<g class="Saturn">
	  <circle cx="150" cy="150" r="70" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="80" cy="150" r="4.5"/>
	</g>
	<g class="Uranus">
	  <circle cx="150" cy="150" r="110" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="40" cy="150" r="5.112"/>
	</g>
	<g class="Neptune">
	  <circle cx="150" cy="150" r="140" fill="none" stroke="var(--theme-color, #42b983)" stroke-miterlimit="10" stroke-width=".5"/>
	  <circle cx="10" cy="150" r="4.96"/>
	</g>
<!--	周期a	轨道半径(天文单位)	英文名		行星半径
水星	0.24	0.38				Mercury		2440
金星	0.62	0.72				Venus		6052
地球	1		1					Earth		6378
火星	1.9		1.52				Mars		3398
木星	11.8	5.2					Jupiter		71492
土星	29.5	9.54				Saturn		60268
天王星	84		19.218				Uranus		25559
海王星	164.8	30.06				Neptune		24788
-->
  <style>
  #orrery {
    transform: rotateY(30deg) rotateX(50deg) rotateZ(0deg);
    transform-origin: 50% 50%;
    fill: var(--theme-color, #42b983);
    overflow: hidden;
	max-height: 100vh;
  }
  .Mercury, .Venus, .Earth, .Mars, .Jupiter, .Saturn, .Uranus, .Neptune {
    animation-name: spin;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
    animation-play-state: running;
    transition-property: opacity;
    transition-duration: 1s;
    transition-timing-function: linear;
    transform-origin: 50% 50%;
  }
  .Mercury {
    animation-duration: 0.24s;
  }
  .Venus {
    animation-duration: 0.62s;
  }
  .Earth {
    animation-duration: 1s;
    stroke: #01a1e2;
    fill: #01a1e2;
  }
  .Mars {
    animation-duration: 1.9s;
  }
  .Jupiter {
    animation-duration: 11.8s;
  }
  .Saturn {
    animation-duration: 29.5s;
  }
  .Uranus {
    animation-duration: 84s;
  }
  .Neptune {
    animation-duration: 164.8s;
  }
  @keyframes spin {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(-360deg);
    }
  }
</style>
</svg>


<svg class="_bgm_play_icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="200" height="200" onclick="_playbgm();">
<defs>
<style type="text/css">
._bgm_play_icon {
    width: 30px;
    height: 30px;
    position: absolute;
    top: 10px;
    left: 10px;
    cursor: pointer;
}
._bgm_play_icon path{
	fill: var(--theme-color, #42b983);
}
</style>
</defs>
<path d="M534.528 114.688c6.144 38.912 6.144 90.112 49.152 139.264 32.768 38.912 67.584 71.68 92.16 104.448 32.768 40.96 55.296 92.16 55.296 143.36 0 81.92-40.96 165.888-67.584 210.944h-12.288c18.432-43.008 57.344-114.688 55.296-190.464-2.048-45.056-18.432-86.016-45.056-120.832-30.72-38.912-81.92-69.632-126.976-73.728v452.608c0 36.864-22.528 67.584-53.248 92.16-30.72 24.576-69.632 38.912-106.496 38.912-22.528 0-43.008-6.144-57.344-18.432-16.384-12.288-24.576-30.72-24.576-51.2 0-32.768 22.528-65.536 53.248-90.112 30.72-24.576 69.632-40.96 100.352-40.96 28.672 0 51.2 4.096 67.584 18.432v-614.4h20.48z m0 0"></path>
<path d="M512 20.48c270.336 0 491.52 221.184 491.52 491.52S782.336 1003.52 512 1003.52 20.48 782.336 20.48 512 241.664 20.48 512 20.48m0-20.48C229.376 0 0 229.376 0 512s229.376 512 512 512 512-229.376 512-512S794.624 0 512 0z"></path>
</svg>



<!-- 封面背景图片
![](_media/bg.png)
-->

<!-- 封面背景颜色
![color](#f0f0f0)
-->