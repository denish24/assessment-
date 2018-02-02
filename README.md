importjava.util.Stack;
	
	
	publicclassSortStack {
	    publicstaticStack<Integer>sort(Stack<Integer>s) {
	        if (s.isEmpty()) {
	            return s;
	        }
	        int pivot =s.pop();
	
	
	        Stack<Integer> left =newStack<Integer>();
	        Stack<Integer> right =newStack<Integer>();
	        while (!s.isEmpty()) {
	            int y =s.pop();
	            if (y < pivot) {
	                left.push(y);
	            } else {
	                right.push(y);
	            }
	        }
	        sort(left);
	        sort(right);
	
	
	        Stack<Integer>tmp=newStack<Integer>();
	        while (!right.isEmpty()) {
	            tmp.push(right.pop());
	        }
	        tmp.push(pivot);
	        while (!left.isEmpty()) {
	            tmp.push(left.pop());
	        }
	        while (!tmp.isEmpty()) {
	            s.push(tmp.pop());
	        }
	
	        return s;
	    }
	    
	    publicstaticvoidmain(String[] args) {
	        Stack<Integer> s =newStack<Integer>();
	        s.push(17);
	        s.push(42);
	        s.push(88);
	
	
	        
	        for (inti=0; i<stack.size(); i++) {
	            System.out.println(stack.get(i));
	        }
	        System.out.println();
	        
	        Stack<Integer>sortedStack= sort(stack);
	        for (inti=0; i<sortedStack.size(); i++) {
	            System.out.println(sortedStack.get(i));
	        }
	        System.out.println();
	    }

