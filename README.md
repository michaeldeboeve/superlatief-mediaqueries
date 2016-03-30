# Superlatief Mediaqueries

> A set of mediaqueries for Sass, Stylus and Less

## Docs


### Viewport

###### Sass
```sh
$bp-screen: if(variable-exists(screen), $bp-screen, 'only screen');
```

###### Stulus
```sh
$bp-screen ?= 'only screen';
```

###### Less
```sh
@bp-screen: 'only screen';
```


### bp(), above(), below(), aboveHeight(), belowHeight()

###### Sass
```sh
@mixin bp($min, $mq: 'max-width', $type: $bp-screen) { … }

.foo {
	@include bp(960px, 'min-width', 'only screen') {
		…
	}
}

Shortcuts:
@include above($min, $type: $screen) { … }
@include below($max, $type: $screen) { … }
@include aboveHeight($min, $type: $screen) { … }
@include belowHeight($max, $type: $screen) { … }
```

###### Stulus
```sh
bp($min, $mq = 'max-width', $type = $screen)
	…

.foo
	+bp(960px, 'min-width', 'only screen')
		…

Aliases:
+above($min, $type: $screen) { … }
+below($max, $type: $screen) { … }
+aboveHeight($min, $type: $screen) { … }
+belowHeight($max, $type: $screen) { … }
```

###### Less
```sh
.above(@min, { … })
.below(@max, { … })
.aboveHeight(@min, { … })
.belowHeight(@max, { … })

.foo {
	.above(960px,{
		…
	})
}
```

### between(), betweenHeight()

###### Sass
```sh
@mixin between($min, $max, $type: $screen) { … }
@mixin betweenHeight($min, $max, $type: $screen) { … }

.foo {
	@include between(960px, 1024px, 'only screen') {
		…
	}
}
```

###### Stulus
```sh
between($min, $max, $type: $screen) { … }
betweenHeight($min, $max, $type: $screen) { … }
	…

.foo
	+betweenHeight(960px, 1024px, 'only screen')
		…
```

###### Less
```sh
.between(@min, @max, { … })
.betweenHeight(@min, @max, { … })

.foo {
	.between(960px, 1024px,{
		…
	})
}
```


### landscape(), portrait()

###### Sass
```sh
@mixin landscape() { … }
@mixin portrait() { … }

.foo {
	@include landscape() {
		…
	}
}
```

###### Stulus
```sh
landscape() { … }
portrait() { … }
	…

.foo
	+landscape()
		…
```

###### Less
```sh
.landscape({ … })
.portrait({ … })

.foo {
	.landscape({
		…
	})
}
```


### hdpi(), res(), x2(), x3()

###### Sass
```sh
@mixin hdpi($ratio: 1.25) { … }

.foo {
	@include hdpi(2) {
		…
	}
}

Aliases:
@include res(2) { … }
@include x2() { … }
@include x3() { … }
```

###### Stulus
```sh
hdpi($ratio = 1.25) { … }
	…

.foo
	+hdpi(2)
		…

Aliases:
+res(2) { … }
+x2() { … }
+x3() { … }
```

###### Less
```sh
.hdpi(@ratio: 1.5, { … })

.foo {
	.hdpi(2, {
		…
	})
}

Aliases:
.res(2,{ … })
.x2({ … })
.x3({ … })
```