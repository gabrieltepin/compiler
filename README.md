# Setup
## Build
In project folder, execute:

`make`

## Run
After building the application, run in project folder:

`./compile SCRIPT_NAME -o OUTPUT_FILE_NAME`

There are also examples already set in test folder. For a quick check to the application, execute:

`./compile test/simple_example -o output`

Then, the output to the corresponding code would be:
#### Lexical Analysis

<table>
<tr>
<th>Coding example </th>
<th>Corresponding lexical tokens output</th>
</tr>
<tr>
<td>

```C++
function factorial(n: integer) : integer {
	var result: integer;
    result = 1;

	while(n > 0){
		result = result * (n - 1);
        n = n - 1;
	}

	return result;
}
```

</td>
<td>

```txt
input_file_name: test/simple_example
output_file_name: output
8 
48 ID id=0 
27 
48 ID id=1 
19 
10 
28 
19 
10 
25 
16 
48 ID id=2 
19 
10 
20 
48 ID id=2 
22 
46 INT id=0 1 
20 
17 
27 
48 ID id=1 
32 
46 INT id=1 0 
28 
25 
48 ID id=2 
22 
48 ID id=2 
41 
27 
48 ID id=1 
39 
46 INT id=2 1 
28 
20 
48 ID id=1 
22 
48 ID id=1 
39 
46 INT id=3 1 
20 
26 
18 
48 ID id=2 
20 
26 
50 
```
</td>
</tr>
</table>

#### Syntactical Analysis

<table>
<tr>
<th>Coding example </th>
<th>Corresponding syntactical output</th>
</tr>
<tr>
<td>

```C++
function factorial(n: integer) : integer {
	var result: integer;
    result = 1;

	while(n > 0){
		result = result * (n - 1);
        n = n - 1;
	}

	return result;
}
```

</td>
<td>

```txt
BEGIN_FUNC null 1 0
	LOAD_REF null
	DUP
	LOAD_CONST 0
	STORE_REF null	DE_REF null	POP
	L0
	LOAD_REF null
	DE_REF null
	LOAD_CONST 1
	GT
	TJMP_FW L1
	LOAD_REF null
	DUP
	LOAD_REF null
	DE_REF null
	LOAD_REF null
	DE_REF null
	LOAD_CONST 2
	SUB
	MUL
	STORE_REF null	DE_REF null	POP
	LOAD_REF null
	DUP
	LOAD_REF null
	DE_REF null
	LOAD_CONST 3
	SUB
	STORE_REF null	DE_REF null	POP
	JMP_BW L0
L1
	LOAD_REF null
	DE_REF null
	RET
END_FUNC
```
</td>
</tr>
</table>
