# assignment2-Suddakanti
# Sravan Suddakanti
### Vizag
Rushikonda beach is widely known for its **golden sands** and tidy waves of **Bay of Bengal**. With its vast stretch of waters, Rushikonda beach is the perfect place to enjoy water sports like **swimming, water skiing and wind surfing**. Lots of people, coconut water and bhel puri available and **egg maggie** is very famous food there.Rushikonda beach famous for its **maggie**

--------------------------------------------------------------------------

# Vishakpatnam International Airport is the closest airport to my food locationss

Vishakapatnam International Airport,
Vishakapatnam,603103

Turn right onto N Oak Trafficway
2.3 mi

Continue onto Burlington St
 Pass by Save A Lot (on the left)

Turn left onto E 9th St
Destination will be on the right

 ### Some food items

* EGG MAGGIE
* CHICKEN BIRIYANI
* COCONUT HALVA
* CHICKEN MAGGIE

[myself](https://github.com/Sravan46/assignment2-Suddankanti/blob/bf592cb9aca583311ff98f8a62e7a20d78efcaa7/AboutMe.md)

-----------------------------------------------

# Sports

Cricket, Badminton, Basketball and Table Tennis are the sports which I would like to recommend to anyone, who is intrested in some physical activity.

|  Name       |  Location   | Amount|
|-------------|-------------|-------|
|  Cricket    | Hughes      |  $69  |
|  Badminton  | Rec         |  $40  |
|  Basketball | Rec         |  $4   |
|TableTennis  |  Recr       |  $3   |

----------------------------------------------------

# Quotes

> The greatest glory in living lies not in never falling, but in rising every time we fall. -Nelson

> The way to get started is to quit talking and begin doing. -Walt Disney

--------------------------------------------

# Dynamic Programming

>Dynamic Programming (commonly referred to as DP) is an algorithmic technique for solving a problem by recursively breaking it down into simpler subproblems and using the fact that the optimal solution to the overall problem depends upon the optimal solution to it's individual subproblems.

More information on Dynamic Programming (https://www.interviewbit.com/courses/programming/topics/dynamic-programming)

        int m, n;
        vector<long long> dp_before(n), dp_cur(n);
        long long C(int i, int j);
        // compute dp_cur[l], ... dp_cur[r] (inclusive)
        void compute(int l, int r, int optl, int optr) {
        if (l > r)
        return;

        int mid = (l + r) >> 1;
        pair<long long, int> best = {LLONG_MAX, -1};

        for (int k = optl; k <= min(mid, optr); k++) {
        best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
        }

        dp_cur[mid] = best.first;
        int opt = best.second;

        compute(l, mid - 1, optl, opt);
        compute(mid + 1, r, opt, optr);
        }

        int solve() {
        for (int i = 0; i < n; i++)
        dp_before[i] = C(0, i);

        for (int i = 1; i < m; i++) {
        compute(0, n - 1, 0, n - 1);
        dp_before = dp_cur;
        }

        return dp_before[n - 1];
        }

More Details: (https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html)
