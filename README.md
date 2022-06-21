function runProgram(input){
    var input = input.split("\n")
    var [n,car]  = input[0].split(" ").map(Number)
        var arr = input[1].split(" ").map(Number)
       // console.log(car)
        arr.sort(function(a,b){return a-b});
        //console.log(arr)
        var ans = 0
        var coun=0
        for(var i = 0; i <arr.length;i++)
        {
            if(ans<car && arr[i] != 0)
            {
                ans =arr[i] + ans
               // console.log(ans)
                coun++
            }
             
        }
        if(ans > car)
        {
            console.log(coun-1)
        }
        else if (ans==car)
        {
            console.log(coun)
        }
        else
        {
            console.log(coun)
        }
    }
     
    
    





if(process.env.USER === ""){
    runProgram('');
}
else {
    process.stdin.resume();
    process.stdin.setEncoding("ascii");
    let read = ""
    process.stdin.on("data", function (input) {
        read += input; 
    }); 
    process.stdin.on("end",function(){
        read= read.replace(/\n$/, "");
        read = read.replace(/\n$/, "");
        runProgram(read);
    });
    process.on("SIGINT" , function (){
        read = read.replace(/\n$/, "");
        runProgram(read);
        process.exit(0);
    });
}
