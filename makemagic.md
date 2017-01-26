# Make~~file~~ magic. 

## So why do I need a Makefile?

You might find glory in typing your compiler, flags includes framesworks and whatnots.

This would be fine if you were a [scribe](https://en.wikipedia.org/wiki/Scribe). not a [wizard](https://en.wikipedia.org/wiki/Magician_(fantasy)).

You, being a wizard, can preform this magical ritual:

```BASH
mkdir magic_circle
cd magic_circle
echo "#include <unistd.h>\nint main(void){write(1,\"Firebolt!\",9);}" > lv_1_firebolt.c
gcc -Wall -Wextra -Werror lv_1.firebolt.c -o pew
./pew
```

And expect the outcome: `Firebolt!` on your console.

Makefile magic is important for this reason, you will want to change that fireball.

When you do you will have to invoke yet again:
`gcc -Wall -Wextra -Werror lv_1.firebolt.c -o pew`
`gcc -Wall -Wextra -Werror lv_4.lightningbolt.c -o nasty_zap`
`gcc -Wall -Wextra -Werror lv_13.moltenlake.c -o grill`

Every time you change the outcome of your cantrip `./pew` or a particular `./grill` or `./zap`.

You may already know this trick:

`alias prep_spell="gcc -Wall -Wextra -Werror"`

To shorten your invokation to:

`prep_spell lv_2.whoopass.c -o open_can`

With a Makefile you can make this process much more magical.

After all, aliases are so [rogue](https://en.wikipedia.org/wiki/Thief_(character_class)). To each their own...

You must prepare your magic.

Create a `Makefile` in your current folder.

`touch Makefile`

Note how it is an UPPERCASE M.

This isn't important.

On some systems `makefile` will even run before it when you invoke make.

This is important. You can run anything as a makefile with:

`make -f "Spellbook" <target>`

Invoke make in another folder:

`make -C inner_circle <target>`

Let's invoke make.

`make <target>`

We will hear a whisper in warning from the [error log](https://en.wikipedia.org/wiki/Plane_(Dungeons_%26_Dragons)#The_Elemental_Chaos).

`make: *** No rule to make target '<target>'.  Stop.`

The goal at hand was to `make` the `<target>`

You may now choose your prefered spell editor.

You can [make it on your own from here](https://www.gnu.org/software/make/manual/make.html)

[Always google your neighbor](https://learnxinyminutes.com/docs/make/)

### The rest. Coming soon(tm) -- All rights released ([qst0](http://qst0.com))
