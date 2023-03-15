# stack-using-queues
void QueueStack :: push(int x)
{
        // Your Code
       if(!q2.empty())
       {
           while(!q2.empty())
           {
               q1.push(q2.front());
               q2.pop();
           }
       }
       q1.push(x);
}
//Function to pop an element from stack using two queues. 
int QueueStack :: pop()
{
        // Your Code
        int n=q1.size();
          if(n==0){
          return -1;
          }
          int i=1;
          while(i<n)
          {
              q2.push(q1.front());
              q1.pop();
              i++;
          }
          int res=q1.front();
          q1.pop();
          while(!q2.empty())
          {
              q1.push(q2.front());
              q2.pop();
            }
         return res;
}
