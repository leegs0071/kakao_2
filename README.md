# kakao

2. 다트 게임(난이도: 하)

카카오톡에 뜬 네 번째 별! 심심할 땐? 카카오톡 게임별~

카카오톡 게임별의 하반기 신규 서비스로 다트 게임을 출시하기로 했다. 다트 게임은 다트판에 다트를 세 차례 던져 그 점수의 합계로 실력을 겨루는 게임으로, 모두가 간단히 즐길 수 있다.
갓 입사한 무지는 코딩 실력을 인정받아 게임의 핵심 부분인 점수 계산 로직을 맡게 되었다. 다트 게임의 점수 계산 로직은 아래와 같다.
다트 게임은 총 3번의 기회로 구성된다.
각 기회마다 얻을 수 있는 점수는 0점에서 10점까지이다.
점수와 함께 Single(S), Double(D), Triple(T) 영역이 존재하고 각 영역 당첨 시 점수에서 1제곱, 2제곱, 3제곱 (점수^1 , 점수^2 , 점수^3 )으로 계산된다.
옵션으로 스타상(*) , 아차상(#)이 존재하며 스타상(*) 당첨 시 해당 점수와 바로 전에 얻은 점수를 각 2배로 만든다. 아차상(#) 당첨 시 해당 점수는 마이너스된다.
스타상(*)은 첫 번째 기회에서도 나올 수 있다. 이 경우 첫 번째 스타상(*)의 점수만 2배가 된다. (예제 4번 참고)
스타상(*)의 효과는 다른 스타상(*)의 효과와 중첩될 수 있다. 이 경우 중첩된 스타상(*) 점수는 4배가 된다. (예제 4번 참고)
스타상(*)의 효과는 아차상(#)의 효과와 중첩될 수 있다. 이 경우 중첩된 아차상(#)의 점수는 -2배가 된다. (예제 5번 참고)
Single(S), Double(D), Triple(T)은 점수마다 하나씩 존재한다.
스타상(*), 아차상(#)은 점수마다 둘 중 하나만 존재할 수 있으며, 존재하지 않을 수도 있다.
0~10의 정수와 문자 S, D, T, *, #로 구성된 문자열이 입력될 시 총점수를 반환하는 함수를 작성하라.
입력 형식

“점수|보너스|[옵션]”으로 이루어진 문자열 3세트.
예) 1S2D*3T
점수는 0에서 10 사이의 정수이다.
보너스는 S, D, T 중 하나이다.
옵선은 *이나 # 중 하나이며, 없을 수도 있다.
출력 형식
3번의 기회에서 얻은 점수 합계에 해당하는 정수값을 출력한다.
예) 37
입출력 예제

예제	dartResult	answer	설명
1	1S2D*3T	37	1^1 * 2 + 2^2 * 2 + 3^3
2	1D2S#10S	9	1^2 + 2^1 * (-1) + 10^1
3	1D2S0T	3	1^2 + 2^1 + 0^3
4	1S*2T*3S	23	1^1 * 2 * 2 + 2^3 * 2 + 3^1
5	1D#2S*3S	5	1^2 * (-1) * 2 + 2^1 * 2 + 3^1
6	1T2D3D#	-4	1^3 + 2^2 + 3^2 * (-1)
7	1D2S3T*	59	1^2 + 2^1 * 2 + 3^3 * 2
문제 해설

문자열 처리String Manipulation를 묻는 문제입니다. 앞에서부터 한 글자씩 잘라서 처리할 수 있고, 또는 간단한 컴파일러를 만들듯이 토큰화Tokenizing와 의미 분석Semantic Analysis을 통해 어렵지 않게 계산할 수 있습니다.
점수 중에는 한 자리뿐만 아니라 두 자리인 10점도 포함되어 있기 때문에 한 글자씩 잘라서 처리할때는 그 부분에 유의해야겠네요. 토큰화로 처리할 때는 정규식을 사용하면 비교적 쉽게 잘라낼 수 있습니다. S, D, T는 각각 원점수, 제곱, 세제곱으로 처리하고 스타상은 두 배로 계산하면 됩니다. 참, 아차상은 마이너스 점수라는 점에 유의하세요.
이 문제의 정답률은 73.47%입니다. 앞서 비밀지도 보다는 낮지만 그래도 많은 분들이 잘 풀어주셨습니다.
