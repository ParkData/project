package day0421;

import java.util.Scanner;

//import java.util.Arrays;

//import java.util.Scanner;

//# 강의 내용 => 핵심 코드 정리
//

/*
 * day0422 - lunchmental
 * 
 * int retry=0;
		System.out.println("암산");
		do {
			int x = (int)(Math.random()*100)+1;
			int y = (int)(Math.random()*100)+1;
			int z = (int)(Math.random()*100)+1;
			
			int num = (int)(Math.random()*4);
			
			int as = 0;
			
			switch (num) {
			case 0:
				as = x+y+z;
				break;
			case 1:
				as = x+y-z;				
				break;
			case 2:
				as = x-y+z;								
				break;
			case 3:				
				as = x-y-z;								
				break;
			}
			while (true) {
				System.out.print( x+( (num<2) ? "+" : "-") +
								  y + ( (num%2==0) ? "+" : "-") +
								  z + " = ");
			int an = sc.nextInt();
			if (an==as) break;
			System.out.println("오답");
			} 
			System.out.println("정답");
			System.out.println("재도전(1)/중지(0)");
			retry = sc.nextInt();
			sc.nextLine();
			
		} while (retry==1);
		System.out.println("종료");
 */

/*
 * day0423 - dicegame
 * 
 * 			while (true) {
			d1 = rd.nextInt(6)+1;
			d2 = rd.nextInt(6)+1;
			
			System.out.println("("+d1 + "," +d2 +")");
			if (d1+d2==5) {
				System.out.println("주사위 두 개의 합이 5가 나왔으므로 게임을 종료합니다.");
				break;
			}
 */

/*
 * day0422 - monthcal
 * 
 * 		int last=-1;	// 이전 월
		int ct = 0;
		
		- 월(month) 중복 제거
		do {
			int month;
			do {	// 직전 월과 같은 월이면 반복 / 같은 달이 아니면 do~while 벗어남
				month = (int)(Math.random()*12);
			} while(month==last);
			last = month;
			
		- 월(month) 입력	
			while (true) {
				System.out.println(month);
				System.out.print((month+1) + "월 : ");
				String qus = sc.nextLine();
				
				if (qus.equals(monthString[month])) break; 	// 정답
				System.out.println("오답입니다.");
			}
			System.out.println(ct +"번째 시도 : " +  "정답입니다. >> 재도전(1) : 종료(0) : ");
			retry = sc.nextInt();
			sc.nextLine();
		} while (retry==1);
		System.out.println("프로그램 종료");
 * 
 */

/*
 * day0422 - day
 * 
 * 		
 * 		int re=0;
		Scanner sc = new Scanner(System.in);
		String[] day = {"일","월","화","수","목","금","토"};
		String[] eng = {"sunday","monday","tuesday","wednesday",
		"thursday","friday","saturday"};	// 영어 소문자 인식
		
		int last = -1;	// 이전 월
		
		// 중복 제거
		do {
			int num;
			do {		// 직전 월과 같은 월이면 반복 / 같은 달이 아니면 while문 벗어남
				num = (int)(Math.random()*7);
			} while(num==last);		// 직전 월과 같은 월일 경우 while문을 벗어나지 않는다.
			last=num;				// 직전 월과 다른 월일 경우 while문을 빠져나온 다음, last값은 num값이 된다.
			
			int id = 0;									// 인덱스 값 설정(num이 day[id]에 들어있는 수인지를 알아내기 위함)
			for (int i = 0; i < day.length; i++) {		// for문으로 num과 day[id]의 모든 값과 비교
				id = i;									// day[i] = day[id] => 인덱스 i와 id 값을 일치시킨다.
				if (id==num) {							// num이 id(i)에 들어있는 수일 경우
					day[id] = day[num];					// day[id]값은 곧 day[num]값이 된다.
					System.out.print(day[num]+"요일을 영어 소문자로 입력하시오. : ");
					// num : 0 => day[0(=num)] : 일 .... num : 6 => day[6] : 토
				}
			
				}
				//  if와 for문을 아예 빠져나온 후 while문에서 입력 값 설정
				while (true) {		
					String input = sc.next();
					if (input.equals(eng[num])) {
						suc++;							// 성공횟수 카운트
						break;							// input 입력 값이 eng[num]에 들어있는 값과 같을 경우 while문을 바로 빠져나옴
					}  else {
						System.out.println("오답");		// 오답일 경우 정답을 입력할 때까지 while문을 벗어나지 않음
						fail++;							// 실패횟수 카운트
					}
									
				}
				
				System.out.println("정답! / 재도전(1), 종료(0)");
				re = sc.nextInt();	// 1입력할 경우 재도전, 0입력할 경우 반복문 벗어나서 종료
				sc.nextLine();		// 에러 방지(엔터 제거용)
			}while (re==1);
			
			System.out.println("성공 / 실패 횟수 : " + suc + " , " + fail);
			System.out.println("종료");
/*

/*
 * day0421 - ex07
 * 
 * 		for (int i = 0; i < arr.length; i++) {
			arr[i] = rd.nextInt(10);
			for (int j = 0; j < i; j++) {	**j < i	(length를 넣을 경우 인덱스 -1이 출력되면서 에러 발생)
				if (arr[j]==arr[i]) {	 i와 j를 비교할 때 중복되는 값이 나오면
					i--;				i에서 1을 빼준다.(다른 값이 나올 때까지)
				}
			}
			
		}
		
		// 재출력
		for (int i = 0; i < arr.length; i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println();
 */

/*
 * 	day0421 - ex06as
 * 
 *  		for (int i = 0 i < arr.length; i++) {	// while문이 for문 안에 들어있음 
													// while문에서 아웃될 경우 for(i)문으로 돌아감
 *  
 * 		 	int j;	// for문용
 * 
			do {
				j=0;
				arr[i] = rd.nextInt(10);
				System.out.println(arr[i]);
				for (j = 0; j < i; j++) {
					if (arr[j]==arr[i]) {
						break;
				}
			} 
					
			} while(j<i);		// 계속 do문으로 돌아가다가 i와 j의 인덱스 값이 모두 최종값이 될 경우 do를 거쳐서 for문으로 돌아감
			
			=> 0	1	 2    3    4
			   5    2 	 2
			   
			   i	2
			   j	0 => 1(중복) => break; => while(j<i)
			
 */

/*
 * 	day0420 - ex03as
 * 
 *   int fee=2500;

		int age = input();
		double rate = feeCalc(age);
		output(age, fee, rate);
	}
	
	static int input() {
		int age=0;
		Scanner sc = new Scanner(System.in);
		age = sc.nextInt();
		return age;
	}

	static double feeCalc(int age) {
		double rate=0.0;
		if (age>=65) {
			rate=0.0;
		} else if (age>=20) {
			rate=1;
		} else if (age>=14) {
			rate=0.75;
		} else if (age>=4) {
			rate=0.5;
		} else {
			rate=0.0;
		}
		return rate;
		
	}
	
	static void output(int age, int fee, double rate) {
		System.out.println(age + "세 요금은 " + (int)(fee*rate)+"원");
	}
}
	
	day0420 - ex04  / 선택정렬 (오름차순, 내림차순)
	
	for (int i = 0; i < num.length-1; i++) {
			int id = i;  // id=0
			for (int j = i+1; j < num.length; j++) { // num[0]을 비교할 필요가 없기 때문에 i+1을
													// 시작값으로 설정한다.
				if (num[id]>num[j])		// j는 num[1]에서 num[4]까지 돈다.
										// 즉, num[id]는 num[1],[2],[3],[4]까지의 값과 모두 비교하는 것이다.
					
										// ex)num[id(=0)]의 값이 num[1]보다 크면 num[id]는 num[1]로 바뀐다.
										// 마찬가지로, num[id]가 num[1]로 바뀌었을때, num[2]와 비교해서 
										// num[2]의 값이 더 작으면 num[id]값은 num[2]값으로 바뀐다.
										// 이 과정에서 num[4]까지의 값을 비교하여, 가장 작은 인덱스의 값이
										// num[id]에 저장된다. 
					id=j;				// => num[id] = num[j]
				
				}
				if (id != i) {
					int tmp = num[id];
					num[id] = num[i];
					num[i] = tmp;
				}
				
			
			System.out.println(i+1+"회전 : " + Arrays.toString(num));
	

 */


//	day0419 - ex07
//
//	/* 출력된 숫자가 배열에 몇 개 들어있는지 구하기
//		 * 랜덤 함수
//		 * ex) 4446579753
//		 * 0 : 0 
//		 * 1 : 1
//		 * ....
//		 * 9 : 1
//		 * 
//		 */
//
//	for (int i = 0; i < num.length; i++) {
//			num2[num[i]]++;		// num2[i] 값에 num[i]의 값을 넣고, 
//								// num[i]의 값(0~9)이 num2[i]에도 들어있을 경우 갯수를 카운팅한다.
//		}
//		for (int i = 0; i < num2.length; i++) {
//			System.out.println(i + " : " + num2[i]+"개");
//		}
//	}
//}
//
//	day0419 - ex06
//
//	/*
//		 * 배열 + 랜덤 사용(1~10) => 10개 출력
//		 * 크기 순으로 재정렬(단, 결과값만이 아닌 과정값도 출력) 
//		 * 
//		 * 1344213843
//		 * 1342134438
//		 * 1321344348
//		 * 1213343448
//		 * 1123344448
//		 */
//
//		int temp = 0;
//		
//		for (int i = 0; i < num.length; i++) {
//			boolean ch = false;
//			for (int j = 0; j < num.length-1; j++) {
//				if (num[j] > num[j+1]) {
//					temp = num[j];
//					num[j] = num[j+1];
//					num[j+1] = temp;
//					ch = true;
//				}
//			}
//			if (!ch) break;		// 중첩 for문을 돌면서 ch 값이 모두 false가 나올 경우 반복문을 빠져나온다.
//								// (=자리 바꿈이 더 이상 발생하지 않을 경우 반복문을 빠져나와서 최종값을 출력한다.)
//								
//								
//	day0419 - Arrays ex08
//
//		// 선택정렬 (오름차순, 내림차순)
//
//		for (int i = 0; i < data.length-1; i++) {
//			int minid = i;
//			for (int j = i+1; j < data.length; j++) {
//				if (data[minid]>data[j]) {
//					minid = j;
//				}
//			}
//			int tmp = data[minid];
//			data[minid] = data[i];
//			data[i] = tmp;
//		}
//	
//	day0419 - Arrays ex07
//	
//		/*
//		 * 주어진 2차원 배열의 데이터보다 가로와 세로로 1이 더 큰 배열을 생성해서
//		 * 배열의 행과 열의 마지막 요소에 각 열과 행의 총합을 저장하고
//		 * 출력하는 프로그램을 완성하시오.
//		 */
//	
//		int[][] rs = new int[score.length+1][score[0].length+1];
//		
//		for (int i = 0; i < score.length; i++) {
//			for (int j = 0; j < score[i].length; j++) {
//				rs[i][j] = score[i][j];
//				rs[i][rs[0].length-1] += score[i][j];
//				rs[rs.length-1][j] += score[i][j];
//				rs[rs.length-1][rs.length-3] += score[i][j];
//			}
//			System.out.println();
//		}
//	
//	day0419 - Arrays ex06
//		/*
//		 * 배열 answer에 담긴 데이터를 읽고 각 숫자의 개수를 세어서
//		 * 개수만큼 '*'를 찍어서 그래프를 그리는 프로그램이다.
//		 * 알맞은 코드를 넣어서 완성하시오.
//		 */							
//		/*
//		 * 3***
//		 * 2**
//		 * 2**
//		 * 4****
//		 */						
//								
//		int[] as = {1,4,4,3,1,4,4,2,1,3,2,};
//		
//		int[] ct = new int[4];
//		
//		for (int i = 0; i < as.length; i++) {
//			ct[as[i]-1]++;
//		}
//		for (int i = 0; i < ct.length; i++) {
//			System.out.print(ct[i]);
//			for (int j = 0; j < ct[i]; j++) {
//			System.out.print("*");	
//			}
//			System.out.println();
//		}							
//	
//		
//	day0419 - Arrays ex05	
//		/*
//		 * 다음은 거스름돈을 몇 개의 동전으로 지불할 수 있는지를 계산하는 문제이다.
//		 * 변수 money의 금액을 동전으로 바꾸었을 때 각각 몇 개의 동전이 필요한지
//		 * 계산해서 출력하라.
//		 * 단, 가능한 한 적은 수의 동전으로 거슬러 주어야 한다. (1)에 알맞은
//		 * 코드를 완성하시오.
//		 * (hint) 나눗셈 연산자와 나머지 연산자 사용
//		 */						
//		
//		int rest = 0;
//		for (int i = 0; i < coin.length; i++) {
//			int num = money/coin[i];
//			money %= coin[i];
//			System.out.println(coin[i] + "원 : " + num);
//			
//		}				
//							
//	day0419 - Arrays ex03
//	
//		for (int i = 0; i < arr.length; i++) {
//			for (int j = 0; j < arr[i].length; j++) {
//				total += arr[i][j];
//				cnt++;
//			}
//			
//			ag = total / (float)cnt;
//		}
//
//	day0419 - Arrays ex02
//	
//		for (int i = 0; i < score.length; i++) {
//			int sum=0;
//			double ag=0;
//			System.out.print(i + "\t");
//			kort += score[i][0];
//			engt += score[i][1];
//			matht += score[i][2];
//			for (int j = 0; j < score[i].length; j++) {
//				
//				sum += score[i][j];
//				
//				System.out.print(score[i][j] + "\t");
//			}
//
//
//	day0415 - Q3as
//	
//			*****
//			 ***
//			  *
//			 ***
//			*****	
//
//		 for (int i = 0; i < 3; i++) {
//			for (int j = 4; j > 4-i; j--) {
//				System.out.print(" ");
//			}
//			for (int j = 5; j > (i*2); j--) {
//				System.out.print("*");
//			}
//			System.out.println();
//		}
//		 
//		 for (int i = 1; i < 3; i++) {
//			for (int j = 0; j < 2-i; j++) {
//				System.out.print(" ");
//			}
//			for (int j = 0; j < (i*2)+1; j++) {
//				System.out.print("*");
//			}
//		System.out.println();
//	   }
//
//
//			 *
//			**
//		   ***
//		  ****
//		 *****
//
//		for (int i = 0; i < 5; i++) {
//	   		for (int j = 0; j < 4-i; j++) {
//				System.out.print(" ");
//			}
//	   		for (int j = 0; j <= i; j++) {
//				System.out.print("*");
//			}
//	   		System.out.println();
//	   	}
//
//
//		day0412 - ex03
//
//		  // 입력, 출력 0
//		  public static void main(String[] args) {
//      
//		  int num = add(10,20);
//		  
//		  System.out.println(num);
//		  
//	   }
//	   
//	   static int add(int i,int j) {
//		  
//		  return i+j;
//		  
//	   }						
//				
//		// 입력 0, 출력 x
//		
//		  public static void main(String[] args) {
//      
//		  add(10,20);
//	   }
//	   
//	   static void add(int i,int j) {
//		  
//		  System.out.println(i+j);
//		  
//	   }
//		
//		// 입력 x, 출력 0
//		
//		 public static void main(String[] args) {
//      
//		  int num = add();
//		  
//		  System.out.println(num);
//	   }
//	   
//	   static int add() {
//		  
//		  return 10+20;
//		  
//	   }
//
//		// 입력, 출력 x
//		
//		public static void main(String[] args) {
//      
//		  add();
//	   }
//	   
//	   static void add() {
//		  System.out.println(30);
//	   }
//
//
//
//
//
//
//
//
//				
//								
//								
//								