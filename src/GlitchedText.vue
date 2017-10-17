<template>
		<div class="glitch" :data-text="text" :style="[glitchStyles]" v-html="text"></div>
</template>

<script>
import grained from 'grained'

export default {
	name: 'glitched-text',
	props: {
		text: {
			type: [Number, String],
			default: null
		},
		color: {
			type: [Number, String],
			default: null
		},
		fontSize: {
			type: Number,
			default: 24
		}
	},
	computed: {
		glitchStyles () {
			if (this.color && this.fontSize) {
				return {
					color: `${this.color}`,
					fontSize: `${this.fontSize}px`
				}
			} else if (this.color) {
				return {
					color: `${this.color}`
				}
			} else if (this.fontSize) {
				return {
					fontSize: `${this.fontSize}px`
				}
			}
		}
	}
}
</script>

<style lang="scss">
$blue: #00FDFF;
$red: #FF0000;
.glitch {
  color: white;
  font-size: 50px;
  font-weight: 600;
  text-transform: uppercase;
  font-family: Helvetica;
  margin: 0;
  z-index: 3;
  position: absolute;
  opacity: 1;
  animation: blink 6s linear infinite;
  letter-spacing: 5px;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  width: 100%;
  text-align: center;
  
  
  &:before, &:after {
    display: block;
    position: absolute;
    content: attr(data-text);
    top: 0;
    left: 0;
    transform: translate(0,0);
    height: 100%;
    width: 100%;
    overflow: visible;
  }
  
  &:before {
    text-shadow: -2px 0 $blue;
    z-index: -1;
    // background-color: rgba(black, .5);
    transform: translate(0,0);
    animation: glitch 6s linear infinite;
  }
  &:after {
    text-shadow: 2px 0 $red;
    z-index: -2;
    // background-color: rgba(black, .5);
    transform: translate(0,0);
    animation: glitch-2 6s linear infinite;
  }
}

@keyframes glitch {
  0% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(-10px,0);
  }
  1% {
    clip: rect(70px, 9999px, 80px, 0);
    transform: translate(30px,0);
  }
  2% {
    clip: rect(80px, 9999px, 90px, 0);
    transform: translate(-30px,0);
  }
  3% {
    clip: rect(20px, 9999px, 30px, 0);
    transform: translate(10px,0);
  }
  4% {
    clip: rect(50px, 9999px, 60px, 0);
    transform: translate(-35px,0);
  }
  5% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(15px,0);
  }
  6% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(-5px,0);
  }
  7% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(0,0);
    color: white;
  }
  8% {
    color: $blue;
    transform: translate(-50px, 0);
  }
  10% {
    color: $blue;
    transform: translate(-50px, 0);
  }
  11% {
    color: $blue;
    transform: translate(0, 0);
  }
  12% {
    color: white;
  }
  13% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(-10px,0);
  }
  14% {
    clip: rect(70px, 9999px, 80px, 0);
    transform: translate(30px,0);
  }
  15% {
    clip: rect(80px, 9999px, 90px, 0);
    transform: translate(-30px,0);
  }
  16% {
    clip: rect(20px, 9999px, 30px, 0);
    transform: translate(10px,0);
  }
  17% {
    clip: rect(50px, 9999px, 60px, 0);
    transform: translate(-35px,0);
  }
  18% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(15px,0);
  }
  19% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(-5px,0);
  }
  20% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(0,0);
    color: white;
  }
  21% {
    color: lime;
    transform: translate(-50px, 0);
  }
  23% {
    color: lime;
    transform: translate(-50px, 0);
  }
  25% {
    color: lime;
    transform: translate(0, 0);
  }
  26% {
    color: white;
  }
  to {

    transform: translate(0,0);
  }
}
@keyframes glitch-2 {
  0% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(10px,0);
  }
  1% {
    clip: rect(70px, 9999px, 80px, 0);
    transform: translate(20px,0);
  }
  2% {
    clip: rect(80px, 9999px, 90px, 0);
    transform: translate(20px,0);
  }
  3% {
    clip: rect(20px, 9999px, 30px, 0);
    transform: translate(10px,0);
  }
  4% {
    clip: rect(50px, 9999px, 60px, 0);
    transform: translate(15px,0);
  }
  5% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(20px,0);
  }
  6% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(0,0);
  }
  7% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(0,0);
    color: white;
  }
  8% {
    color: rgba($red, .8);
    transform: translate(50px, 0);
  }
  10% {
    color: rgba($red, .8);
    transform: translate(50px, 0);
  }
  11% {
    color: rgba($red, .8);
    transform: translate(0, 0);
  }
  12% {
    color: white;
  }
  13% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(10px,0);
  }
  14% {
    clip: rect(70px, 9999px, 80px, 0);
    transform: translate(20px,0);
  }
  15% {
    clip: rect(80px, 9999px, 90px, 0);
    transform: translate(20px,0);
  }
  16% {
    clip: rect(20px, 9999px, 30px, 0);
    transform: translate(10px,0);
  }
  17% {
    clip: rect(50px, 9999px, 60px, 0);
    transform: translate(15px,0);
  }
  18% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(20px,0);
  }
  19% {
    clip: rect(0px, 9999px, 0px, 0);
    transform: translate(0,0);
  }
  20% {
    clip: rect(0px, 9999px, 100px, 0);
    transform: translate(0,0);
    color: white;
  }
  21% {
    color: rgba(pink, .8);
    transform: translate(50px, 0);
  }
  23% {
    color: rgba(pink, .8);
    transform: translate(50px, 0);
  }
  25% {
    color: rgba(pink, .8);
    transform: translate(0, 0);
  }
  26% {
    color: white;
  }
  to {
    transform: translate(0,0);
  }
}
@keyframes blink {
  0% {
    opacity: 1;
  }
  3% {
    opacity: 0;
  }
  6% {
    opacity: .4;
  }
  9% {
    opacity: 0;
    left: 50%;
    color: white;
  }
  12% {
    opacity: 1;
  }
  15% {
    opacity: .2;
  }
  18% {
    opacity: 1;
  }
  to {
    opacity: 1;
  }
}
</style>