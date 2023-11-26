Լաբորատոր աշխատանք 1

1. mkdir lab1, touch file.txt file1.txt file2.txt file3.txt, mkdir dir1 dir2։
2. Printed all files that end with .txt and second printed everything and showed an   error about .txt
3. ls -1 f???.txt
4. ls -1 file*[[:digit:]]* 
5. ls -1 *([[:lower:]]|[1-2]).txt
6. cp /etc/passwd
7. mv lab1 new
   mv new dir1
   mv dir1/new dir2
8. mv dir2 dir3
   mv dir3 dir1
9. mv dir1/dir3/new ../lab1
10. rm -r lab1


Լաբորատոր աշխատանք 2

1. 
    cat > file1: Այս հրամանը ստեղծում կամ վերագրանցում է «file1» անունով ֆայլ և թույլ է տալիս տեքստ մուտքագրել այդ ֆայլը: Կարող եք մուտքագրել տեքստ, սեղմել Ctrl+D (մուտքագրումն ավարտելու համար) և բովանդակությունը պահել ֆայլում:
    cat file1: Այս հրամանը ցուցադրում է «file1» ֆայլի բովանդակությունը տերմինալի էկրանին: Այսպիսով, եթե «file1» ֆայլը գոյություն ունի և պարունակում է որոշակի տեքստ, դուք կտեսնեք այդ տեքստը էկրանին:
    cat < file1: Այս հրամանը օգտագործում է < նիշը` մուտքագրումը վերահղելու համար: Այսինքն, cat հրամանը կարդում է «file1» ֆայլի մուտքագրումը և ցուցադրում այն ​​տերմինալի էկրանին: Սա համարժեք է cat file1 հրամանին:

2.  touch file1.txt file2.txt file3.txt
    cat file1.txt file2.txt file3.txt > final.txt
3.  ls -l /home/student | grep -c "^-"
4.  sort file1.txt file2.txt file3.txt > sorted_files.txt
5.  ls -lSh home/student | head -n 15 
6.  lab1 % ls -l home/student > home/student/ls.txt 
7.  echo "secret text" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
    echo "frperg grkg" | tr 'a-zA-Z' 'n-za-mN-ZA-M'
8.  echo "Student’s home directory is {home_dir}." > home.txt
    sed 's|{home_dir}|/home/student|g' home.txt
9.  echo -e "Line 1\nLine 2\nLine 3\nLine 4\nLine 5" > file4.txt
    sed -n '2,4p' file4.txt
10. sed '2,4d' file4.txt


Լաբորատոր աշխատանք 3

1.  ls -l /etc | grep -E "^[0-9]"
2.  echo -e "Hello\nWorld\nGoodbye\nSolo\nYellow\nHello\nBelow" > sample_file.txt
    grep -E '^[^5]+$' sample_file.txt | grep 'lo$'
3. 
    grep -h '[A-Z]' dirlist*.txt. Այս հրամանն օգտագործում է grep՝ գտնելու տողեր        ֆայլերում, որոնք պարունակում են A-ից Z-ից առնվազն մեկ մեծատառ: -h տարբերակը grep-ին հրահանգում է չտպել ֆայլերի անունները, միայն տողերը:

    grep -h '[-AZ]' dirlist*.txt. Այս հրամանում grep-ը փնտրում է տողեր, որոնք պարունակում են կա՛մ «-» նիշը, կա՛մ A և Z մեծատառերը: Այստեղ սխալն այն է, որ «-» նիշը ներսում է: քառակուսի փակագծերը հատուկ նշանակություն չունեն և մեկնաբանվում են բառացի: Այսպիսով, այս հրամանը փնտրում է տողեր, որոնք պարունակում են «-» նիշը կամ A և Z մեծատառերը:

    grep -h '^[A-Z]' dirlist*.txt. Այստեղ grep-ը փնտրում է տողեր, որոնք սկսվում են A-ից մինչև Z ցանկացած մեծատառով: Նախշի սկզբում գտնվող «^»-ը նշում է տողի սկիզբը:

    grep -h '[^A-Z]' dirlist*.txt. Այս հրամանն օգտագործում է grep՝ գտնելու տողեր, որոնք պարունակում են ցանկացած այլ նիշ, բացի A-ից Z մեծատառերից: Այս համատեքստում քառակուսի փակագծերի ներսում գտնվող «^» նիշը հակադարձում է պայմանը, որպեսզի այն փնտրում է տողեր, որտեղ մեծատառեր չկան:

4.  grep '^\(bz\|zip\)' dirlist-bin.txt
    grep '^\(bz\|zip\)' dirlist-sbin.txt
5. 
    grep -Eh '^(bz|gz|zip)' dirlist*.txt. Այս հրամանը օգտագործում է ընդլայնված կանոնավոր արտահայտություններ -E դրոշով: Այն փնտրում է տողեր, որոնք սկսվում են «bz», «gz» կամ «zip» բառերով: Այստեղ ^ նշանակում է տողի սկիզբ, իսկ (bz|gz|zip) նշանակում է «bz» կամ «gz» կամ «zip»: -h դրոշն ասում է grep-ին չտպել ֆայլերի անունները, այլ միայն տողերը:

    grep -Eh '^bz|gz|zip' dirlist*.txt. Այս հրամանը նաև օգտագործում է ընդլայնված կանոնավոր արտահայտություն -E դրոշով, բայց փակագծերի այլ բաշխումով: Այն փնտրում է տողեր, որոնք սկսվում են «bz»-ով կամ պարունակում են «gz» կամ «zip» տողի ցանկացած կետում: Այստեղ ^bz նշանակում է, որ տողը պետք է սկսվի «bz»-ով և | առանձնացնում է «gz» և «zip» այլընտրանքները:
6.  
    email="test@test.com" && if [[ $email =~ '^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z| a-z]{2,}$' ]]; then echo "Valid email."; else echo "Invalid email."; fi
7. 
    ipv4="192.168.0.1" && if echo "$ipv4" | grep -Pq '^((25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$'; then echo "Valid IPv4 address."; else echo "Invalid IPv4 address."; fi

8. 
    echo "level" > palindromes.txt
    echo "deified" >> palindromes.txt
    echo "radar" >> palindromes.txt
    echo "civic" >> palindromes.txt
    echo "redder" >> palindromes.txt
    echo "madam" >> palindromes.txt

    echo "deleveled" >> palindromes.txt
    echo "repaper" >> palindromes.txt
    echo "rotator" >> palindromes.txt
    echo "reifier" >> palindromes.txt
    echo "reviver" >> palindromes.txt

    grep -E '^(.)(.)(.).\3\2\1$' palindromes.txt
9.  date -jf "%m/%d/%Y" "01/02/1970" "+%Y-%m-%d"
10. echo "0xx 12-34-56" | sed -E 's/0xx ([0-9]{2}-[0-9]{2}-[0-9]{2})/(\1)/'s


Լաբորատոր աշխատանք 4

1. 
    touch file.txt
    chmod 744 file.txt
2.  chmod a+x file.txt
3.  chmod o-rwx file.txt
4. 
    chmod 600 file.txt

    chmod u=rw,go= file.txt
5. 
    # Ստեղծել dir դիրեկտորիան ու սահմանել իրավունքները
    mkdir dir
    chmod 744 dir

    # Դիրեկտորիայում ստեղծել file.txt ֆայլը
    touch dir/file.txt

    # Ուղարկել ինֆորմատիվ հաղորդագրություն
    echo "Նոր ֆայլը ստեղծվել է" > dir/file.txt

6. 
    # Դիրեկտորիայում ստեղծել file1.txt և file2.txt ֆայլերը
    touch dir/file1.txt dir/file2.txt

    # Բոլոր ֆայլերին սահմանելու իրավունքները -rwxrw-rw-
    chmod 764 dir/*
7. 
    umask 027
8. 
    umask 600
    umask 0022
9. 
    #!/bin/bash

    # Սահմանել իրավունքները
    chmod -rwxr--r-- /home/student

    # Արտածել /home/student դիրեկտորիայի ֆայլերի ցուցակը
    ls /home/student
10. 
    mkdir ~/bin
    echo '#!/bin/bash

    # Սահմանել իրավունքները
    chmod -rwxr--r-- /home/student

    # Արտածել /home/student դիրեկտորիայի ֆայլերի ցուցակը
    ls /home/student' > ~/bin/myscript.sh
    chmod +x ~/bin/myscript.sh
    myscript.sh

Լաբորատոր աշխատանք 5

1. #!/bin/bash
    str="Hello"
    echo $str2
    echo $str2. Այս հրամանում մենք փորձում եք տպել $str2 փոփոխականի արժեքը:
    Այնուամենայնիվ, մենք չունեք $str2 անունով փոփոխական, մենք միայն սահմանել ենք փոփոխական $str: 
    Հետևաբար այս հրամանը դուրս կգա դատարկ տող:
    echo ${str}2
    echo ${str}2. Այս հրամանը օգտագործում է գանգուր փակագծեր՝ հստակորեն նշելու փոփոխականի 
    անվան սահմանը: Այսպիսով, մենք կփորձենք դուրս բերել str փոփոխականի արժեքը՝ դրան կցված «2»-ով:
2. 
    echo $(( (5 * 5 * 4) / 10 ))
3. 
    echo "The balance for user $USER is: $5.00"
    Այս հրամանում $5-ը կմեկնաբանվի որպես հինգերորդ հրամանի տողի արգումենտ, 
    այլ ոչ թե որպես «USER» անունով փոփոխականի արժեք։
    echo "The balance for user $USER is: \$5.00"
    Այստեղ \-ն օգտագործվում է $ նիշից խուսափելու համար, 
    ինչը նշանակում է, որ հաջորդ նիշը (5) կմեկնաբանվի որպես տողի մաս, 
    այլ ոչ թե որպես փոփոխական:
    $USER-ը կփոխարինվի օգտագործողի փոփոխականի ընթացիկ արժեքով։
4. 
    echo '$USER $((2 + 2)) $(ls)'
    Այս հրամանում օգտագործվում են միայնակ չակերտներ ('), ինչը նշանակում է, 
    որ դրանց ներսում գտնվող բոլոր նիշերը կմեկնաբանվեն բառացիորեն, և փոփոխականները կամ արտահայտությունները, 
    ինչպիսիք են $USER և $((2 + 2)) չեն ընդլայնվի: 
    Բացի այդ, $(ls) արտահայտությունը նույնպես կմեկնաբանվի բառացի:
    echo "$USER $((2 + 2)) $(ls)"
    Այս հրամանը օգտագործում է կրկնակի չակերտներ (")՝ թույլ տալու համար, 
    որ փոփոխականները մեկնաբանվեն և ls հրամանը կատարվի $(ls) արտահայտության ներսում։
    Ենթադրենք, որ $USER-ը պարունակում է ընթացիկ օգտվողի անունը (օրինակ՝ «օգտանուն»): 
    Այնուհետև այս հրամանի արդյունքը կարող է լինել.
        username 4 file1 file2 file3 ...

    Այնտեղ, որտեղ «username»-ը ներկայիս օգտվողի անունն է, «4»-ը $((2 + 2)) արդյունքն է, 
    իսկ «file1 file2 file3 ...»-ը ls հրամանի արդյունքն է:
    Այսպիսով, երկրորդ հրամանը, օգտագործելով կրկնակի չակերտներ, 
    թույլ էր տալիս փոփոխական ինտերպոլացիա և հրամանի կատարում տողերի ներսում, 
    մինչդեռ առաջին հրամանը պահում էր նիշերի բառացի իմաստները միայնակ չակերտների ներսում:
5. 
    current_directory=$(pwd)
    cat <<EOF
    Current Directory: $current_directory
    Text files in the current directory:
    $(ls -1 *.txt)
    Number of text files: $(ls -1 *.txt | wc -l)
    EOF
6. #!/bin/bash

    # Գումարող ֆունկցիա
    sum_numbers() {
        # Կառուցել փոփոխականը, որը պարունակելու է գումարվող թվերը
        result=$(( $1 + $2 ))
        
        # Վերադարձնել արդյունքը
        echo $result
    }

    # Թվերի մուտքագրում
    read -p "Մուտքագրեք առաջին թիվը: " num1
    read -p "Մուտքագրեք երկրորդ թիվը: " num2

    # Կանչել ֆունկցիան ու տպել արդյունքը
    result=$(sum_numbers $num1 $num2)
    echo "Թվերի գումարը՝ $result"
7. 
    #!/bin/bash

    count_files() {
        directory=$1
        if [ -d "$directory" ]; then
            file_count=$(find "$directory" -type f | wc -l)
            echo "Տեղեկություն՝ $directory դիրեկտորիայում առկա ֆայլերի քանակը՝ $file_count"
        else
            echo "Սխալ. Տվյալներին ստացված դիրեկտորիան չի գտնվել:"
        fi
    }

    # Կանչել ֆունկցիան
    count_files "/path/to/your/directory"
8. 
    #!/bin/bash

    # Ստեղծել նոր ֆայլ
    touch new_file.txt

    # Ստուգել ֆայլի թույլտվությունը
    if [ -r new_file.txt ] && [ -w new_file.txt ] && [ -x new_file.txt ]; then
        echo "Ֆայլը կարդալու, գրելու և կատարելու թույլտվություն ունի:"
    else
        echo "Ֆայլը չունի համապատասխան թույլտվություն:"
    fi
9. 
    #!/bin/bash

    # Խնդիրը լուծելու համար տրվող թվերը
    num1=$1
    num2=$2

    # Կորոշել մեծագույնը
    if [ $num1 -gt $num2 ]; then
        max=$num1
    else
        max=$num2
    fi

    # Արտածել մեծագույնը
    echo "Մեծագույնը՝ $max"

10.
    #!/bin/bash

    # Տրված թիվը
    number=$1

    # Կորոշումը
    if [ $((number % 2)) -eq 0 ]; then
        echo "Զույգ"
    else
        echo "Կենտ"
    fi

Լաբորատոր աշխատանք 6

1. 
    #!/bin/bash

    # Տրված թիվը
    number=$1

    # Ստուգումը
    if [[ $number =~ ^[0-9]+$ ]]; then
        if [ $number -gt 0 ]; then
            echo "Թիվը դրական է"
        elif [ $number -lt 0 ]; then
            echo "Թիվը բացասական է"
        else
            echo "Թիվը 0 է"
        fi
    else
        echo "Չվավեր թիվ"
    fi
2. 
    #!/bin/bash

    # Տրված թիվը
    number=$1

    # Ստուգումը
    if ((number > 0)); then
        echo "Թիվը դրական է"
    elif ((number < 0)); then
        echo "Թիվը բացասական է"
    else
        echo "Թիվը 0 է"
    fi
3. 
    #!/bin/bash

    # Տրված թիվը
    number=$1

    # Ստուգումը
    if ((number % 2 == 0 && number % 3 == 0 && number % 5 == 0)); then
        echo "Թիվը բազմապատիկ է 2-ի, 3-ի և 5-ի"
    else
        echo "Թիվը չի բազմապատիկ 2-ի, 3-ի և 5-ի"
    fi
4. same
5. 
    echo ' "Hello, this is my script!"' > myscript.sh && chmod +x myscript.sh
6. 

    #!/bin/bash

    # Ստուգել, թե արդյոք "dir" անվանումով դիրեկտորիան գոյություն ունի թե ոչ
    if [ -d "dir" ]; then
        echo "դիրեկտորիան գոյություն ունի"
    else
        # Ստեղծել "dir" անվանումով դիրեկտորիա
        mkdir "dir"
        echo "դիրեկտորիան ստեղծվել է"
    fi
7. 
    #!/bin/bash

    # Ներմուծել թվերը
    read -p "Մուտքագրեք թիվը: " number
    read -p "Մուտքագրեք միջակայքի ստորին սահմանը: " lower_limit
    read -p "Введите верхнюю границу интервала:  " upper_limit

    # Ստուգել, թե թիվը գտնվում է սահմանված միջակայքում
    if [ "$number" -ge "$lower_limit" ] && [ "$number" -le "$upper_limit" ]; then
        echo "Թիվը գտնվում է $lower_limit-ից $upper_limit-ը"
    else
        echo "Թիվը չգտնվում $lower_limit-ից $upper_limit-ը"
    fi
8. 
    #!/bin/bash

    # Ներմուծել արժեքը և ստուգել, թե համընկնում է "Secret"-ի հետ
    read -s -p "Մուտքագրեք արժեքը: " REPLY

    if [ "$REPLY" = "Secret" ]; then
        echo "Ճիշտ արժեք: Secret"
    else
        echo "Սխալ արժեք"
    fi
9. 
    #!/bin/bash

    # Ներմուծել ֆայլի անունը
    read -p "Մուտքագրեք ֆայլի անունը: " filename

    if [[ "$filename" =~ ^[A-Za-z1-9.-_]+$ ]]; then
        echo "Ներմուծված ֆայլի անունը վավեր է:"
    else
        echo "Սխալ ֆայլի անուն: Ստեղծել Նոր ֆայլ: "
        touch "$filename"
    fi
10. 
    #!/bin/bash

    # Ներմուծել արժեքները
    read -p "Մուտքագրեք թիվը: " num1
    read -p "Մուտքագրեք գործողությունը (+, -, *, /, **): " operator
    read -p "Մուտքագրեք այլ թիվը: " num2

    # Ստուգել արժեքների քանակը
    if [[ $(echo "$num1 $num2 $operator" | wc -w) -ne 3 ]]; then
        echo "Սխալ՝ ներմուծված արժեքների քանակը չի համընկնում պահվածին"
        exit 1
    fi

    # Գործողության արդյունքը
    case $operator in
        "+")
            result=$(($num1 + $num2))
            ;;
        "-")
            result=$(($num1 - $num2))
            ;;
        "*")
            result=$(($num1 * $num2))
            ;;
        "/")
            result=$(($num1 / $num2))
            ;;
        "**")
            result=$(($num1 ** $num2))
            ;;
        *)
            echo "Սխալ՝ անհայտ գործողություն"
            exit 1
            ;;
    esac

    # Արտածել արդյունքը
    echo "Գործողությունը ($num1 $operator $num2) հավասար է $result"

Լաբորատոր աշխատանք 7

1. #!/bin/bash

    # Սկրիպտի մոդիֆիկատորը պահպանելու համար
    declare -i i=0

    while [ $i -le 20 ]; do
    # Ստուգելուն եթե i-ն զույգ է, ապա արտածել
    if [ $((i % 2)) -eq 0 ]; then
        echo $i
    fi
    # i-ն բարձրացնել մեկով
    ((i++))
    done
2. #!/bin/bash
    # Իրականացնել until ցիկլը
    counter=0
    until [ $counter -gt 20 ]; do
        if [ $((counter % 2)) -eq 0 ]; then
            echo $counter
        fi
        ((counter++))
    done
3. #!/bin/bash
    # Ստեղծել փոփոխականը որպես ինդեքս
    index=0

    
    while true; do
        # Արտածել ինդեքսի քառակուսը
        echo $((index ** 2))

        # Խնդիրը ավարտել, եթե արտածվող թիվը գերազանցում է 1000
        if [ $((index ** 2)) -gt 1000 ]; then
            break
        fi

        # Բարձրացնել ինդեքսը
        ((index++))
    done
4. #!/bin/bash

    # Գտնել [0, 20] միջակայքի զույգ թվերը
    for ((i=0; i<=20; i+=2)); do
        if [ $((i % 2)) -eq 0 ]; then
        echo $i
    fi
    done
5. #!/bin/bash

    while true; do
        # Ստանալ մուտքագրված ամբողջ թիվը կամ "q" տառը
        read -p "Enter an integer number, or enter q to quit: " input

        # Ստուգել, թե արդյոք մուտքագրվել է "q"
        if [[ $input == "q" ]]; then
            echo "Exiting the program..."
            break
        fi

        # Ստուգել, թե մուտքագրվածը ամբողջ թիվ է
        if [[ $input =~ ^[0-9]+$ ]]; then
            # Արտածել թիվը և դրա կրկնապատիկը
            echo "Entered number: $input, Its double: $((input * 2))"
        else
            # Եթե մուտքագրվածը չի լինելու ամբողջ թիվ, նորից խնդրել մուտքագրել
            echo "Invalid input. Please enter a valid integer."
        fi
    done
6. #!/bin/bash

    directory="/home/student"
    counter=1

    find "$directory" -maxdepth 1 -type f -name "*.txt" | while read -r file; do
        # Նոր ֆայլի անվան ձևավորում համարով
        new_filename="${directory}/file${counter}.txt"

        #Ֆայլի վերանվանավորում
        mv "$file" "$new_filename"

        echo "Ֆայլը վերանվանվել է: $file  $new_filename"

        ((counter++))
    done

7. #!/bin/bash

    for ((i = 0; i <= 30; i += 3)); do
        echo $i
    done
8. #!/bin/bash

    for file in /home/student/*; do
        [[ -e "$file" ]] || continue

        # Արտածել ֆայլի անունը
        echo $(basename "$file")
    done
9. ls /home/student > listing.txt
   ./find_min_word listing.txt

    #!/bin/bash

        while [[ -n $1 ]]; do
        if [[ -r $1 ]]; then
        min_len=0
        for i in $(cat $1); do
        len=$(echo $i | wc -c)
        if (( len > min_len )); then
        min_len=$len
        fi
        done
        echo "$1: ($min_len characters)"
        fi
        shift
        done
10. #!/bin/bash

    if [ "$#" -eq 0 ]; then
        echo "Մուտքագրեք ֆայլերի անունները։"
        exit 1
    fi

    # Ներմուծված բոլոր ֆայլերի անունները
    files=("$@")

    # Ֆայլերի ստուգում
    for file in "${files[@]}"; do
        # Ստուգել, թե ֆայլը գոյություն ունի թե ոչ
        if [ -e "$file" ]; then
            # Ստուգել, թե ֆայլը կարդալու թույլտվություն ունի թե ոչ
            if [ -r "$file" ]; then
                echo "$file-ը գոյություն ունի և կարդալու թույլտվություն ունի։"
            else
                echo "$file-ը գոյություն ունի, բայց չի կարդալություն։"
            fi
        else
            echo "$file-ը գոյություն չունի։"
        fi
    done

Լաբորատոր աշխատանք 8

1. #!/bin/bash

    while :
    do
        echo "Մուտքագրեք [0, 3] միջակայքի թիվը (0-ավարտել, 1-/home/student ֆայլերի ցուցակ, 2-/home/student ֆայլերի քանակ, 3-աշխատանքային դիրեկտորիա):"
        read choice

        case $choice in
            0)
                echo "Ծրագիրը ավարտվում է։"
                break
                ;;
            1)
                echo "Ֆայլերի ցուցակը /home/student դիրեկտորիայում:"
                ls /home/student
                ;;
            2)
                echo "Ֆայլերի քանակը /home/student դիրեկտորիայում:"
                find /home/student -type f | wc -l
                ;;
            3)
                echo "Աշխատանքային դիրեկտորիան:"
                echo "/home/student/work"
                ;;
            *)
                echo "Սխալ ներմուծում։ Կրկին փորձեք։"
                ;;
        esac
    done
2. #!/bin/bash

    echo "Մուտքագրեք ամիսը (նախընտրեք  ամսվա անունը):"
    read month

    days=0

    case "$month" in
        "հունվար"|"մարտ"|"ապրիլ"|"մայիս"|"հունիս"|"հուլիս"|"օգոստոս"|"սեպտեմբեր"|"հոկտեմբեր"|"նոյեմբեր"|"դեկտեմբեր"|"փետրվար")
            case "$month" in
                "հունվար"|"մարտ"|"մայիս"|"հուլիս"|"սեպտեմբեր"|"դեկտեմբեր"|"օգոստոս")
                    days=31
                    ;;
                "ապրիլ"|"հունիս"|"սեպտեմբեր"|"նոյեմբեր")
                    days=30
                    ;;
                "փետրվար")
                    days=28
                    ;;
            esac
            ;;
        *)
            echo "Ամսաթիվը սխալ է նշված։"
            exit 1
            ;;
    esac

    echo "$month ամիսը ունի $days օր։"
3. #!/bin/bash

    # Ներմուծել արժեքները
    read -p "Մուտքագրեք թիվը: " num1
    read -p "Մուտքագրեք գործողությունը (+, -, *, /, **): " operator
    read -p "Մուտքագրեք այլ թիվը: " num2

    # Ստուգել արժեքների քանակը
    if [[ $(echo "$num1 $num2 $operator" | wc -w) -ne 3 ]]; then
        echo "Սխալ՝ ներմուծված արժեքների քանակը չի համընկնում պահվածին"
        exit 1
    fi

    # Գործողության արդյունքը
    case $operator in
        "+")
            result=$(($num1 + $num2))
            ;;
        "-")
            result=$(($num1 - $num2))
            ;;
        "*")
            result=$(($num1 * $num2))
            ;;
        "/")
            result=$(($num1 / $num2))
            ;;
        "**")
            result=$(($num1 ** $num2))
            ;;
        *)
            echo "Սխալ՝ անհայտ գործողություն"
            exit 1
            ;;
    esac

    # Արտածել արդյունքը
    echo "Գործողությունը ($num1 $operator $num2) հավասար է $result"
4. #!/bin/bash

    # Ստուգել, որ տրված լինի արգումենտ
    if [ "$#" -ne 1  ]; then
        echo "Մուտքագրեք միայն մեկ ֆայլի անունը։"
        exit 1
    fi

    # Ստուգել, որ ֆայլը կարդալու կարգավիճակում է
    if [ ! -r "$1" && ! -e "$1" ]; then
        echo "Ֆայլը չի գտնվել։ Կամ չհաջողվեց կարդալ $1 ֆայլը։"
        exit 1
    else
        # Կարդալ և արտածել ֆայլի պարունակությունը
        cat "$1"
    fi
5. #!/bin/bash

    # Ստանալ արգումենտները
    if [ "$#" -ne 2 ]; then
        echo "Մուտքագրեք երկու ֆայլերի անունները։"
        exit 1
    fi

    # Ստուգել, որ առաջին ֆայլը գոյություն ունի
    if [ ! -e "$1" ]; then
        echo "Առաջին ֆայլը չի գտնվել։"
        exit 1
    fi

    # Ստուգել, որ երկրորդ ֆայլը արդյոք դատարկ չէ
    if [ ! -s "$2" ]; then
        echo "Երկրորդ ֆայլը դատարկ է։"
        exit 1
    fi

    # Ստուգել, որ երկրորդ ֆայլը կարդալու կարգավիճակում է
    if [ ! -r "$2" ]; then
        echo "Երկրորդ ֆայլը հնարավոր չէ կարդալ։"
        exit 1
    fi

    # Կատարել պատճենումը
    cat "$1" > "$2"

    echo "Ֆայլը պատճենված է։"
6. #!/bin/bash

    # Ստանալ թվերը որպես արգումենտներ
    if [ "$#" -ne 2 ]; then
        echo "Մուտքագրեք երկու թվերը։"
        exit 1
    fi

    result=$(($1 + $2))

    echo "Գումարը՝ $result"
7. #!/bin/bash

    # Ստանալ արգումենտներ
    while [ "$#" -gt 0 ]; do
        # Արտածել առաջին արգումենտը
        echo "Արգումենտ՝ $1"
        
        # Բերել հաջորդ արգումենտը
        shift
    done
8. #!/bin/bash

    for arg in "$@"; do
        # Արտածել արգումենտը
        echo "Արգումենտ՝ $arg"
    done
9. #!/bin/bash

    args=("$@")
    if [ $# -eq 0 ]; then
        echo "ՈՒղարկեք առանձին արգումենտները։"
        exit 1
    fi

    # Արտածել թվերի գումարը
    sum=0
    for num in "${args[@]}"; do
        ((sum += num))
    done

    echo "Թվերի գումարը՝ $sum"
10. #!/bin/bash

    if [ $# -eq 0 ]; then
        echo "ՈՒղարկեք արգումենտները։"
        exit 1
    fi

    # Զույգ թվերի քանակի հաշվումը։
    even_count=0
    for num in "$@"; do
        if ((num % 2 == 0)); then
            ((even_count++))
        fi
    done

    echo "Զույգ թվերի քանակը՝ $even_count"











































