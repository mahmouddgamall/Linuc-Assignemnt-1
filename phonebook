#!/bin/bash
clear

c=0
c2=0
Arr=()
Number=()
input="f1.txt"
 
while IFS= read -r line
do
line="$(echo "$line"|tr -d '\n')" 
if [[ $(($c%2)) == 0 ]]
then 
Arr[c/2]="$line"
c=$[$c+1]
else 
Number[$c/2]="$line"
c=$[$c+1]
fi
done < "$input"




#############################################




if [[ $1 == '-i' ]]
then 

clear
echo "Add Contact"

flag=0
read -p "Plz enter  Name " AddedName
SearchCounter=0
for item in ${Arr[*]}
do 
if [[ $item == $AddedName ]]
then 

flag=1
SearchCounter=$[$SearchCounter+1]
else 
SearchCounter=$[$SearchCounter+1]
fi 
done 


if [[ $flag == 1 ]];
then
echo "The name is already added, if you wish to edit it please remove it and add it again"
fi

if [[ $flag == 0 ]];
then


read -p "Plz enter Number: " AddedNumber

size=${#Arr[*]}
Arr[size]=$AddedName
Number[size]=$AddedNumber 


rm -f f1.txt
Counter1=0
for item in ${Arr[*]}
do 
echo $item >>f1.txt 
echo ${Number[$Counter1]}>>f1.txt
Counter1=$[$Counter1+1]
done
fi


elif [[ $1 == '-v' ]]
then 

clear
echo "***************************"
echo "View All"
#########################
##########################
##########################
#view All
Counter1=0
for item in ${Arr[*]}
do 
printf "%s\n" $item
#if [[ $Number!=0 ]]
#then 
printf "%s\n" ${Number[$Counter1]}
Counter1=$[$Counter1+1]
done 


elif [[ $1 == '-e' ]]
then 

clear  
echo "***************************"
echo "Delete All Mode"
Arr=()
Number=()
printf > f1.txt




elif [[ $1 == '-d' ]]
then 


clear 
echo "remove Contact"
#######################
#######################
#######################
#Remove An element
flag=0
read -p "Plz enter  Name " value
SearchCounter=0
for item in ${Arr[*]}
do 
if [[ $item == $value ]]
then 
echo $item

printf "%s\n" ${Number[$SearchCounter]}

unset 'Arr[SearchCounter]'
unset 'Number[SearchCounter]'
unset 'Arr[SearchCounter]'
flag=1
SearchCounter=$[$SearchCounter+1]
else 
SearchCounter=$[$SearchCounter+1]
fi 
done 
if [[ $flag == 1 ]];
then
echo "Delete is done successfully" 
else 
echo "The element does not exist"
fi 


elif [[ $1 == '-s' ]]
then 


clear 
echo "search"

flag=0
read -p "Plz enter  Name " value
SearchCounter=0
for item in ${Arr[*]}
do 
if [[ $item == $value ]]
then 
#echo ${Arr[*]}
#echo ${Number[*]}
echo $item

printf "%s\n" ${Number[$SearchCounter]}

flag=1
SearchCounter=$[$SearchCounter+1]

else 
SearchCounter=$[$SearchCounter+1]
fi 
done 
if [[ $flag == 1 ]];
then
echo "Here is the contact" 

else 
echo "The element does not exist"
fi 

fi

####################
###################
###################

cont=1

while [ $cont == 1 ] && [[ $1 != '-v' ]] && [[ $1 != '-i' ]] && [[ $1 != '-s' ]] && [[ $1 != '-e' ]] && [[ $1 != '-d' ]];
do

echo "Plz chose mode"
echo "1)Add Contact"
echo "2)Remove Contact"
echo "3)View All"
echo "4)Delete All"
echo "5)Exit"  
read -p "Plz enter Choice: " choose

if [[ $choose == 1 ]];
then
clear
echo "Add Contact"
read -p "Plz enter Name: " AddedName
read -p "Plz enter Number: " AddedNumber

size=${#Arr[*]}
Arr[size]=$AddedName
Number[size]=$AddedNumber 
elif [[ $choose == 2 ]];
then 
clear 
echo "remove Contact"
#######################
#######################
#######################
#Remove An element
flag=0
read -p "Plz enter  Name " value
SearchCounter=0
for item in ${Arr[*]}
do 
if [[ $item == $value ]]
then 
echo ${#Arr[*]}
echo ${#Number[*]}
unset 'Arr[SearchCounter]'
unset 'Number[SearchCounter]'
unset 'Arr[SearchCounter]'
#unset 'Number[SearchCounter]'
#unset 'Arr[SearchCounter+1]'
flag=1
SearchCounter=$[$SearchCounter+1]
else 
SearchCounter=$[$SearchCounter+1]
fi 
done 
if [[ $flag == 1 ]];
then
echo "Delete is done successfully" 
else 
echo "The element is not exist"
fi 

elif [[ $choose == 3 ]]
then 
clear
echo "***************************"
echo "View All"
#########################
##########################
##########################
#view All
Counter1=0
for item in ${Arr[*]}
do 
printf "%s\n" $item
#if [[ $Number!=0 ]]
#then 
printf "%s\n" ${Number[$Counter1]}
Counter1=$[$Counter1+1]
done 
##########################
##########################
############################

elif [[ $choose == 4 ]]
then 
clear  
echo "***************************"
echo "Delete All Mode"
Arr=()
Number=()
printf > f1.txt

elif [[ $choose == 5 ]]
then 
clear 
echo "***************************"
echo "Exit Mode"


rm -f f1.txt
Counter1=0
for item in ${Arr[*]}
do 
echo $item >>f1.txt 
echo ${Number[$Counter1]}>>f1.txt
Counter1=$[$Counter1+1]
done

cont=0
else 
echo "plz enter valid choice"

fi 

done 
