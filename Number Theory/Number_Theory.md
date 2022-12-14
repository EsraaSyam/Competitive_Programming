# Number Theory

## Session @ ICPC SCU
[session](https://cisuezedu.sharepoint.com/sites/ICPC-SCULevel12022/_layouts/15/stream.aspx?id=%2Fsites%2FICPC%2DSCULevel12022%2FShared%20Documents%2FGeneral%2FRecordings%2FNumber%20Theory%2D20221124%5F200452%2DMeeting%20Recording%2Emp4&referrer=Teams%2ETEAMS%2DELECTRON&referrerScenario=teamsSdk%2DopenFilePreview)
## 1- sieve prime

- syntax :
```cpp
const int N = 1e7 + 5;
vector < bool > is_prime(N, true);
vector < ll > primes;
void Sieve(){
    is_prime[0] = false;
    is_prime[1] = false;
    for(long long i = 2; i * i < N; i++)
        if(is_prime[i])
            for(int j = 2 * i; j < N; j += i)
                is_prime[j] = false;
 
    for(int i = 0; i < N ; i++){
        if(is_prime[i])
            primes.push_back(i);
    }
}
```
- time complexity : 

     $O(nloglogn)$

- problem

   [Count Primes ](https://leetcode.com/problems/count-primes/)

---
## 2- sieve factorization

- syntax :
```cpp
vector < int > factors;
void sieve_factorization(ll n){
    factors.assign(n + 5 , 2);
    factors[0] = 0;
    factors[1] = 1;
    for(int i = 2 ; i <= n ; i++){
        for(int j = i + i ; j <= n ; j += i) factors[j]++;
    }
}
```
- time complexity

  $nlog(n)$

---
## 3- sieve prime factorization

- syntax:
```cpp
vector < int > prime_factors;
void sieve_prime_factorization(ll n){
     prime_factors.resize(n + 5);
     for(int i = 2 ; i <= n ; i++){
        if(!prime_factors[i]){
            for(int j = i * 2 ; j <= n ; j += i) prime_factors[j]++;
            prime_factors[i] = 1;
        }
     }
}
```

- we use it when problem want only the number of uniqe prime factors
- 
- time complexity

  $nlog(n)$

---
### problem (sieve factorization and sieve prime factorization)

[Is it Number Theory ?!](https://codeforces.com/group/p6hc42ieQe/contest/339245/problem/J)




