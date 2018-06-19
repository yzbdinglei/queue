# queue
bool is_ok(int row)       //判断第row行的c[row]位置是否可以放置皇后   
{  
    for(int j=0;j<row;j++)  
    if(c[row]==c[j]||(row+c[row]==j+c[j])||(row-c[row]==j-c[j]))//判断是否在同一列或者同一对角线上   
    return false;  
    return true;  
 }   
void queue(int row,int n)      
{  
    if(row==n)  
    total++;  
    else  
    {  
        for(int col=0;col<n;col++)  
        {  
            c[row]=col;             //表示第row行的col（即c[row]）位置可以放置皇后   
            if(is_ok(row))  
            queue(row+1,n);  
        }     
    }  
}  
