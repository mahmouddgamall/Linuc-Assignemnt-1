#!/bin/bash


for item in $@
do

if [[ ! -z $item ]]					#check if there is a file in the first argument
then

status=`file $item | cut -d ' ' -f3`					#chech if the file is compressed or not

if [[ $status != 'compressed' ]]
then


tar -zcvf $item.tgz $item										#compress it
rm -r $item													#remove old file/folder
mv $item.tgz ~/TRASH/$item.tgz						#move new compressed file



else
mv $item ~/TRASH/$item										#move compressed file

fi

fi

done




########
val='find -type f -mmin +360 -iname "~/TRASH/$item.tgz"'
if [[ -n $val ]]
then
echo "File yes" 
else 
echo "File no"
fi
#######
#######

touch dummy
year=`stat -c '%y' dummy | cut -c1-4`
month=`stat -c '%y' dummy | cut -c6-7`
day=`stat -c '%y' dummy | cut -c9-10`

rm dummy

test=$[$year-$month]

cd ~/TRASH
touch myls 
ls -lh >myls


input="myls"
skip=0

while IFS= read -r line
do


if [[ $skip == 0 ]]
then
skip=1

else


line="$(echo "$line"|tr -d '\n')"
myfile="$line"
myfile=$(echo $myfile | cut -d ' ' -f9)

year1=`stat -c '%y' $myfile | cut -c1-4`
month1=`stat -c '%y' $myfile | cut -c6-7`
day1=`stat -c '%y' $myfile | cut -c9-10`


dyear=$[$year-$year1]
dmonth=$[$month-$month1]
dday=$[$day-$day1]
if [[ $dyear == 0 ]]
then
if [[ $dmonth == 0 ]]
then
if [[ $dday -ge 2 ]]
then

rm -f $myfile

fi

else
rm -f $myfile
fi

else
rm -f $myfile
fi
fi


done < "$input" 



########
#tar -zxvf result.tgz

