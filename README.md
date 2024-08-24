//hashtable
//first we create a constructor that defines the size of out arrays where we will store the values 
//then we create the hashing system for the array where we take the size into account
//we 

class learninghashtable{
  constructor(size){
    this.table = new Array(size);
    this.size = size;
  }

  hash(key){
    return key% this.size
  }
  insert(key,value){
    let index = this.hash(key);
  if(this.table[index]!==undefined){
    index =(index+1)%this.size;
  }
    this.table[index]= {key,value};
  }

  check(key){
    let index = this.hash(key);
    if(this.table[index] !== undefined){
      return this.table[index].value;
    }
    return 'empty'
  }
}
let test = new learninghashtable(10);
test.insert(12,"this value is 12");
let answer = test.check(12);
console.log(answer);
