<!-- #Question 1
#Define an array of numbers (use any random numbers). Write a program to print only the even numbers of the array. Do not use any library functions, need to do via for loops only
#===>
public class Even {
public static void main(String args[]){
int a[]={1,2,3,4,5,6};
for (int i=0;i<a.length;i++){
if(a[i] % 2 ==0){
System.out.println(a[i]);
}
}
}
}




#Find the maximum consecutive 1's in an array of 0's and 1's.
#=====>
class MaxConsecutive {
public int maxConsecutiveOnes(int[] nums) {
int maxvalue=0, count=0;
for(int i:nums)
 maxvalue = Math.max(maxvalue, count=i ==1 ? count+1: 0);
 return maxvalue;
 }
 }
 
 
 #Suppose you have an array of 101 integers. This array is already sorted and all numbers in this array are consecutive. Each number only occurs once in the array except one #number which occurs twice. Write a js code to find the repeated number.
 #==>
 Class DuplicateNumber{
 public int findDuplicate(int[] nums){
 if(nums.length <=1) 
 return -1;
 int duplicate=nums[0],single=nums[nums[0]];
 while(duplicate != single){
 duplicate = nums[duplicate];
 single=nums[nums[single]];
 }
 if(duplicate != single)
 return -1;
 duplicate=0;
 while(duplicate != single){
 duplicate= nums[duplicate];
 single= nums[single];
 }
 return duplicate;
 }
 }
 
 
 
 
 
 #Question 4
Let’s see we an api url https://my-json-server.typicode.com/typicode/demo/posts
Write a sample code to call this rest api and display the result.
 #==>
 
 import 'dart:convert';

import 'package:flutter/material.dart';
import 'package:myhome_page.dart';


void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  List data;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: Text('fetch data from json file'),
        ),
        body: Center(
          child: FutureBuilder(
            future: DefaultAssetBundle.of(context)
                .loadString('assets/loadjson/details.json'),
            builder: (context, snapshot) {
              // Decode the JSON
              var newData = json.decode(snapshot.data.toString());

              return ListView.builder(
                itemBuilder: (BuildContext context, int index) {
                  return Card(
                    child: Padding(
                      padding: const EdgeInsets.only(
                          top: 32, bottom: 32, left: 16, right: 16),
                      child: Row(
                        mainAxisAlignment: MainAxisAlignment.spaceBetween,
                        children: <Widget>[
                          Column(
                            crossAxisAlignment: CrossAxisAlignment.start,
                            children: <Widget>[
                              InkWell(
                                onTap: () {
                                  Navigator.push(
                                      context,
                                      MaterialPageRoute(
                                          builder: (_) => Welcome()));
                                },
                                child: Text(
                                  newData[index]['id'],
                                  //'Id',
                                  style: TextStyle(
                                      fontWeight: FontWeight.bold,
                                      fontSize: 22),
                                ),
                              ),
                              Text(
                                newData[index]['title'],
                                //'Title',
                                style: TextStyle(color: Colors.grey.shade600),
                              ),
                            ],
                          ),
                         
                        ],
                      ),
                    ),
                  );
                },
                itemCount: newData == null ? 0 : newData.length,
              );
            },
          ),
        ));
  }
}

  
  
  
  
  
###Question 5
Assume there is a object of this format 
var obj = {
 “id” : 4, “name” : “abc”,
 “id” : 10, “name” : “ab2”,
 “id” : 5, “name” : “abc3”,
 “id” : 6, “name” : “abc5”
}
It can be a dictionary or java object, as per your language of choice. But its key/value pair dictionary simply.

Write a code to sort the object by id 
I.e final output should have objected sort by id’s
#==>
  import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
 
class Employee{
    String name;
    String id;
   
    public Employee() {}
   
    public Employee(String name, String id) {
        this.name = name;
        this.id = id;
    }
   
   
    @Override
    public String toString() {
        return "Employee{" + "name=" + name + ", id=" + id  + '}';
    }
 
    //Inner class
    class ComparatorName  implements Comparator<Employee>{
       @Override
        public int compare(Employee obj1, Employee obj2) {
           //sort Employee on basis of name(ascending order)
           return obj1.name.compareTo(obj2.name);
        }
    }
   
 
    //static Inner class
    static class ComparatorId  implements Comparator<Employee>{
       @Override
        public int compare(Employee obj1, Employee obj2) {
           //sort Employee on basis of id(ascending order)
           return obj1.id.compareTo(obj2.id);
        }
    }
 
}
 
  
  
 -->
