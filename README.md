# Phonebook-using-cpp
![image](https://user-images.githubusercontent.com/91861155/211261856-446ae7fe-3a25-443a-a494-325c66165e8b.png)

int main()
{
    char n[20];
    char nam[20];
    char name[10];
    char number[10];
    char gmail[20];
    dlist d1;
    // apply d;
    char ans;
    int ch,a;
    cout<<"**************                                PHONE BOOK                          ********************";
    cout<<"\n\nWHAT IS YOUR NAME?\n";
    cin.getline(name,20);
    cout<<"\n\n!!!!!!!!!!!!!!!!!!!!!!!   WELCOME "<<name<<"   !!!!!!!!!!!!!!!!!!!!!";
    cout<<"\n\n\nLET'S CREATE OUR PHONEBOOK "<<name<<"  \n\n";
    d1.accept();
    d1.sort();
    do
    {
    cout<<"\n\n\n\n1) DISPLAY YOUR PHONE BOOK\n2) INSERT NEW CONTACT\n3) UPDATE DETAILS ON EXISTING CONTACT\n4) DELETE CONTACT\n5) DELETE SAME NAME IN PHONEBOOK\n6) DELETE SAME NUMBERS IN PHONEBOOK\n7) SEARCH\n";
    cin>>ch;
    switch(ch)
    {
    case 2:
    d1.insert();
    d1.sort();
    break;
    
    case 1:
    // d1.sort();
    d1.display();
    break;
    case 3:
    
        cout<<"\n\nENTER THE NAME OF PERSON WHOSE DETAILS YOU WANT TO UPDATE...\n";
        cin>>n;
    d1.update(n);
    d1.sort();
    break;
    case 4:
    cout<<"\nENTER THE NAME YOU WANT TO DELETE FROM PHONEBOOK\n";
    cin>>name;
    d1.deletecontact(name);
    break;
     case 5:
    d1.deletesamename();
    d1.display();
    break;
    case 6:
    d1.deletesamenumber();
    d1.display();
    break;
    case 7:
    do
    {
    cout<<"1.SEARCH BY NAME\n2.SEARCH BY NUMBER\n3.SEARCH BY GMAIL";
    cin>>a;
    switch(a)
    {
        case 1:
        cout<<"ENTER THE NAME TO BE SEARCHED\n";
        cin>>name;
        d1.searchbyname(name);
        break;
        case 2:
        cout<<"ENTER THE NAME TO BE SEARCHED\n";
        cin>>number;
        d1.searchbynumber(number);
        break;
        case 3:
        cout<<"ENTER THE NAME TO BE SEARCHED\n";
        cin>>gmail;
        d1.searchbygmail(gmail);
        break;
        default:cout<<"\nNO PROPER INPUT GIVEN.....\n";
    }
    cout<<"DO YOU WANT TO CONTINUE SEARCHING?????????";
    cin>>ans;
}while(ans=='y');

    break;
    case 8:d1.deletesamegmail();
    d1.display();
    break;
    default:cout<<"\nNO PROPER INPUT GIVEN..\n";
    }
    cout<<"\n\nDO YOU WANT TO CONTINUE OPERATIONS?????????";
    cin>>ans;
}while(ans=='y');
}
