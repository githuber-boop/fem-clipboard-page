# breakpoints scss

$breakpoints-up: (
    'medium':'40em',
    'large':'64em',
    'xlarge':'87.5em',
);

$breakpoints-down: (
    'small':'39.9375em',
    'medium':'63.9375em',
    'large':'87.4375em',
);

@mixin breakpoint($size) {
    @media (min-width: map-get($breakpoint-up,$size)) {
        @content;
    }
}


@mixin breakpoint-down($size) {
    @media (min-width: map-get($breakpoint-down,$size)) {
        @content;
    }
}

# how to use breakpoint
selector {
    @include breakpoint(large){
        styles
    }
}

# how to import 
@forward 'name of file';

# function scss

# rem converter
@function rem($pixels, $context:16){
    @return ($pixels / $context) * 1rem;
}

# how to use
font-size:rem(30);