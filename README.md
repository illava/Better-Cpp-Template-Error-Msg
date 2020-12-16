# Better-Cpp-Template-Error-Msg
A python script to view compiler's ultra long c++ template error messages in foldable html.

## Install

Copy `bettermsg` to executable path.

## Usage

1. Use pipeline`>cat error.log |bettermsg`.
2. Use filename as first parameter `>bettermsg error.log`
3. Use string `>bettermsg "TypeA<TypeB,TypeC<TypeD,TypeE<int,float>,TypeF>::Detail,TypeG<int, float>>::operator()"`

## Example

Code in usage 3 will produce:

```
TypeA<
	 TypeB,
	+TypeC< >::Detail,
	 TypeG<int, float>
>::operator()
```

Click anywhere in line `+TypeC< >::Detail,` and it will expand to

```
TypeA<
	 TypeB,
	-TypeC<
	 	TypeD,
	 	TypeE<int,float>,
	 	TypeF
	 >::Detail,
	 TypeG<int, float>
>::operator()
```

Click any where in line `-TypeC<` and i twill fold.



## Notes

* Expansion is recursive.
* Auto unrolls tail templates. 

## License

MIT License.