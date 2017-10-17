# glitched-text

Repo is based on https://github.com/ianaya89/vue-glitch repo.

## Installation
The vue component can be installed via npm or yarn

### npm 
```
$ npm install @eli5/vue-glitched
```

### yarn
```
$ yarn add @eli5/vue-glitched
```

### CSS

In your main css file add this line of code

```
@import "~@eli5/vue-glitched/dist/client.css";
```

## Usage

Start by importing the component.

```
import GlitchedText from '@eli5/vue-glitched'

export default {
	components: {
		GlitchedText
	}
}
```

In your template file

```
<glitched-text :text="'Glitched text'" :color="'#FFF'" :fontSize="50"></glitched-text>
```