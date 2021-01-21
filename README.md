JEST is use for testing.

you run the project just by typing
`git clone https://github.com/Kashif1Naqvi/JEST-testing-framework.git`
`cd JEST-testing-framework`
`npm install`
then type
`npm install`

```
const sum = require('./sum');

test('add 1 + 2 to equal 3', ()=> {
	expect(sum(1,2)).toBe(3);
})


test("object assignment", () => {

	let data = {
		one : 1
	}
	data['two'] = 2

	expect(data).toEqual({one:1, two:2})
})


test("for loop test", () => {
	for(let i = 1; i < 10; i++){
		expect(i).not.toBe(0);
	}
})


test("nested loop test", ()=>{
	for(let i=1; i<=10; i++){
		for(let j=1; j<=10; j++){
			expect(i + j).not.toBe(0)
		}
	}
})

test('null',() => {
	let n = null;
})

test('undefined', ()=> {
	let n;
	expect(n).toBeUndefined();
})

test("defined", ()=>{
	let n = 1;
	expect(n).toBeDefined();
})

test("true",()=>{
	let n = true
	expect(n).toBeTruthy();
})

test("false",()=>{
	let n =  false;
	expect(n).toBeFalsy()
})


// number

test(" sum 2 + 2 ", () => {
	let value = 2 + 2;
	expect(value).toBeGreaterThan(2.3);
	expect(value).toBeLessThan(5);
	expect(value).toBeLessThanOrEqual(6);
	expect(value).toBeGreaterThanOrEqual(3);

	// toBe() and toEqual() equivalent for numbers

	expect(value).toBe(4);
	expect(value).toEqual(4);
})



// for floating


test("for floating 0.1 + 0.2",()=>{
	let n = 0.1 + 0.2
	expect(n).toBeCloseTo(0.3);
})

// string

test("My name is syed kashif ali naqvi I like codeing",()=>{
	expect('name').not.toMatch(/i/);
	expect('syed kashif').toMatch(/syed kashif/);
	expect('syed').not.toMatch(/kd/);
	expect('codeing').toMatch(/c/);
})



// arrays and iterable

let developer_names = [
	'Sir Syed Murtza shah',
	'Sir Asim',
	'Sir Hassan',
	'Syed kashif',
	'Aqeel Malik',
]

test("test developer names using Jest",()=>{
	expect(developer_names).toContain('Syed kashif'); // write exect array index value
	expect(new Set(developer_names)).toContain('Sir Hassan');
})



// Expection

function Android(){
	throw new Error("you are using wrong JDK");
}


test("compiling android goes as expected!",()=>{
	expect(()=>Android()).toThrow();
	expect(()=>Android()).toThrow(/JDK/);
})

// TESTING ansynchronous


function fetchData(){
	return 'peanut butter';
}


test("this is data peanut butter",done => {
	function callBack(data){
		expect(fetchData(data)).toBe('peanut butter');
		done()
	}
	callBack();
});



beforeEach(()=>console.log("1 beforeEach"));
afterEach(()=>console.log("1 after Each"));
afterAll(()=>console.log("1 after all"));
beforeAll(()=>console.log("1 before all"));
test('',()=>console.log("1 test"));

describe('nested describe!', ()=>{
	beforeAll(()=>console.log('2 inner before all'));
	afterAll(()=>console.log("2 after all"));
	beforeEach(()=>console.log("2 before Each"));
	afterEach(()=>console.log("2 after Each!"));
	test('',()=>console.log("2 test!"))
});


// only run one test

test.only('this will be the only test that runs', ()=>{
	expect(true).toBe(true);
})


```
