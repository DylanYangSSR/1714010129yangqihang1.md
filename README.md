           #文件管理系统 
           
            #include<stdio.h>
            #include<string.h>
            #include<stdlib.h>
            {
            int number;
            char name[10];
            char nature[10];
            int date;
            int size;
            }   
            T[100];
            void input(struct file T[]);//输入
            void show(struct file T[]);//显示
            void find1(struct file T[]);//通过文件名查找
            void find2(struct file T[]);//通过文件号查找
            void add(struct file T[]);//增加
            void modify(struct file T[]);//删除




            int i=0;
            int main()
        {
            int k;
            char choice;
            system("cls");
            while(1)
          {
            printf("               *********************\n");
            printf("               *  请你选择功能     *\n");
            printf("               *  (1).输入数据     *\n");
            printf("               *  (2).显示数据     *\n");
            printf("               *  (3).查找数据     *\n");
            printf("               *  (4).增加一条数据 *\n");
            printf("               *  (5).删除一条数据 *\n");
            printf("               *  (6).退出         *\n");
            printf("               *********************\n");
            scanf("%s",&choice);

            switch(choice)
        {


            case '1':input(T);
                    system("cls");
                    break;
            case '2':show(T);
                    system("pause");
                    system("cls");
                    break;

            case '3':printf("请问你需要使用哪种查找方式\n");
                    printf("1.文件名查找\n");
                    printf("2.文件号查找\n");
                    scanf("%d",&k);
                    if(k==1)
        {
                        find1(T);
                        system("pause");
                        system("cls");
                        break;
        }
                    if(k==2)
        {
                        find2(T);
                        system("pause");
                        system("cls");
                        break;
        }
            case '4':add(T);
                    system("cls");
                    break;
            case '5':modify(T);
                    system("cls");
                    break;

            case '6':return 0;
                     break;
        }
        }

        }


            void input(struct file T[])
        {
            int n;
            printf("请问你需要输入多少组数据\n");
            scanf("%d",&n);
            for(i=0;i<n;i++)
        {
            printf("请你输入文件号\n");
            scanf("%d",&T[i].number);
            printf("请输入文件名\n");
            scanf("%s",T[i].name);
            printf("请输入文件性质\n");
            scanf("%s",T[i].nature);
            printf("请输入文件日期\n");
            scanf("%d",&T[i].date);
            printf("请输入文件大小\n");
            scanf("%d",&T[i].size);
            printf("\n\n");
        }
        }
            void show(struct file T[])//浏览
        {
            int j;
            for(j=0;j<i;j++)
        {
            printf("文件号:");
            printf("%d\n",T[j].number);
            printf("文件名:");
            printf("%s\n",T[j].name);
            printf("文件性质:");
            printf("%s\n",T[j].nature);
            printf("文件日期:");
            printf("%d\n",T[j].date);
            printf("文件大小:");
            printf("%d\n",T[j].size);
        }
        }

            void find1(struct file T[])//通过文件名查找
        {
            char name[10];
            int j;
            printf("请输入您要查找的文件名");
            scanf("%s",name);
            for(j=0;j<i;j++)
        {
            if(strcmp(T[j].name,name)==0)
            break;
        }

            if(j==i)
        {
                printf("查无此文件\n");
        }
            else
        {
                printf("文件号:");
                printf("%d\n",T[j].number);
                printf("文件名:");
                printf("%s\n",T[j].name);
                printf("文件性质:");
                printf("%s\n",T[j].nature);
                printf("文件日期:");
                printf("%d\n",T[j].date);
                printf("文件大小:");
                printf("%d\n",T[j].size);
        }
        }

            void find2(struct file T[])//通过文件号查找
        {
            int number;
            int j;
            printf("请输入你要查找的文件号:\n");
            scanf("%d",&number);
            for(j=0;j<i;j++)
        {
            if(T[i].number==number)
        {
            break;
        }
        }
            if(j==i)
        {
            printf("查无此人\n");
        }
            else
        {
            printf("文件号:");
            printf("%d\n",T[j].number);
            printf("文件名:");
            printf("%s\n",T[j].name);
            printf("文件性质:");
            printf("%s\n",T[j].nature);
            printf("文件日期:");
            printf("%d\n",T[j].date);
            printf("文件大小:");
            printf("%d\n",T[j].size);
        }
        }
            void add(struct file T[])//添加
        {
            char confirm;
            do
        {
            printf("请你输入文件号\n");
            scanf("%d",&T[i].number);
            printf("请输入文件名\n");
            scanf("%s",T[i].name);
            printf("请输入文件性质\n");
            scanf("%s",T[i].nature);
            printf("请输入文件日期\n");
            scanf("%d",&T[i].date);
            printf("请输入文件大小\n");
            scanf("%d",&T[i].size);
            printf("请问是否继续输入*确认请输入Y，任意其他键退出*\n");
            scanf("%s",&confirm);
            i++;
        }
            while(confirm=='Y');
        }
            void modify(struct file T[])//修改
        {
            int j,k,number;
            printf("请输入您要删除的文件号");
            scanf("%d",&number);
            for(j=0;j<i;j++)
        {
            if(T[j].number==number)
            break;
        }
            if(j==i)
            printf("查无此文件");
            else
         {
            for(k=j;k<i-1;k++)
           {
            T[k]=T[k+1];
           }
            i--;
         }
            printf("删除成功\n");
        }
   
