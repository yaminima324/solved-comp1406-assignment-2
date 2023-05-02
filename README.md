Download Link: https://assignmentchef.com/product/solved-comp1406-assignment-2
<br>
In this assignment, you will create 5 objects and get them to interact together.   You will create theatres for which patrons will buy tickets from a box office to watch movies.

<h1>(1) The Movie, Ticket, Theatre and Patron Classes</h1>

You will need to define 4 objects as indicated below.   You must choose appropriate attribute names so that the test program that follows compiles and runs properly.

<ul>

 <li>Define a class called <strong>Movie</strong> that maintains the title of a movie as well as the amount of earnings it has made since it opened at the theatre.</li>

 <li>Define a class called <strong>Theatre</strong> that keeps track of the <strong>Movie</strong> object that is currently playing in that theatre. A theatre should also have a seat capacity and keep track of how many seats have been sold for the movie playing.</li>

 <li>Define a class called <strong>Ticket</strong> that represents a ticket to go and watch a movie. Each ticket is only valid for a specific <strong>Theatre </strong></li>

 <li>Define a class called <strong>Patron</strong> that keeps track of the age of a person as well as the <strong>Ticket</strong> object that he/she has purchased.</li>

</ul>

Write any necessary code so that the following test program works as indicated in the output that follows:

<strong>public class </strong>TestProgram {

<strong>public static void </strong>main(String args[]) {         Movie m = <strong>new </strong>Movie(<strong>“Despicable Me 3”</strong>);

System.<strong><em>out</em></strong>.println(m.<strong>title</strong>);

System.<strong><em>out</em></strong>.println(m.<strong>earnings</strong>);




Theatre theatre = <strong>new </strong>Theatre(3);

System.<strong><em>out</em></strong>.println(theatre.<strong>capacity</strong>);

System.<strong><em>out</em></strong>.println(theatre.<strong>seatsSold</strong>);         theatre.<strong>moviePlaying </strong>= m;




Patron mary = <strong>new </strong>Patron(15);

System.<strong><em>out</em></strong>.println(mary.<strong>age</strong>);

System.<strong><em>out</em></strong>.println(mary.<strong>ticket</strong>);         mary.<strong>ticket </strong>= <strong>new </strong>Ticket(theatre);

System.<strong><em>out</em></strong>.println(mary.<strong>ticket</strong>.<strong>theatre</strong>.<strong>moviePlaying</strong>.<strong>title</strong>);

}

}

Despicable Me 3

The expected output is shown here on the right à<sub>                   0.0 </sub>

Make sure that your code works before you continue.<sub>                   3</sub><sub>  </sub>

0                                                              15                                                               null

Despicable Me 3

<h2>(2) The <strong>BoxOffice</strong> Class<sub>  </sub></h2>

Define a class called <strong>BoxOffice </strong>that keeps track of two theatres for which it sells movie tickets.  The cost of a movie ticket is $6.25 for children under 12 years old, $5.75 for adults 65 years old or more and $12.50 for everyone else.   The box office should also keep track of the movie that has made the most money in the past.

Carefully examine the test program below.   Understand how it is supposed to work.   Then write the necessary methods so that the code runs properly, producing the correct results.   You may NOT alter the test program … the TA will be using it to test your code.   Note that when tickets are sold to patrons, the title of the movie is provided.   You will need to determine which theatre that movie is playing in.   As a hint, you can compare two strings using the<strong> .equals() </strong>method in JAVA as follows:

String s1 = …; String s2 = …; <strong>if</strong> (s1.<strong>equals</strong>(s2))

…; <strong>else </strong>

…;




Note as well in the program below that the <strong>bestMovie()</strong> will either be a previous movie that had the most earnings or one of the current playing movies … whichever has the most earnings.




Here is the test program:




<strong>public class </strong>BoxOfficeTestProgram {

<strong>public static void </strong>main(String args[]) {

<em>// Create a box office with two theatres, each with a capacity of 5 seats         </em>BoxOffice box = <strong>new </strong>BoxOffice(5, 5);




<em>// Open up a couple of new movies at the box office </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“Theatre A opens movie: Justice League”</strong>);         box.<strong>openMovie</strong>(<strong>“Justice League”</strong>, box.<strong>theatreA</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Theatre B opens movie:  Geostorm”</strong>);         box.<strong>openMovie</strong>(<strong>“Geostorm”</strong>, box.<strong>theatreB</strong>);




<em>// Now create some patrons </em>

<em>        </em>Patron p1, p2, p3, p4, p5, p6, p7, p8, p9, p10, p11, p12;         p1 = <strong>new </strong>Patron(15);         p2 = <strong>new </strong>Patron(26);         p3 = <strong>new </strong>Patron(7);         p4 = <strong>new </strong>Patron(72);         p5 = <strong>new </strong>Patron(65);         p6 = <strong>new </strong>Patron(11);         p7 = <strong>new </strong>Patron(19);         p8 = <strong>new </strong>Patron(17);         p9 = <strong>new </strong>Patron(12);         p10 = <strong>new </strong>Patron(14);         p11 = <strong>new </strong>Patron(13);         p12 = <strong>new </strong>Patron(16);




// … continued on the next page … //










<em>// Sell some tickets to the patrons </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“Patron 1 buys ticket for Justice League”</strong>);         box.<strong>sellTicket</strong>(p1, <strong>“Justice League”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Patrons 2,3 and 4 buy tickets for Geostorm”</strong>);         box.<strong>sellTicket</strong>(p2, <strong>“Geostorm”</strong>);         box.<strong>sellTicket</strong>(p3, <strong>“Geostorm”</strong>);         box.<strong>sellTicket</strong>(p4, <strong>“Geostorm”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Geostorm seats remaining: ” </strong>


(box.<strong>theatreB</strong>.<strong>capacity </strong>– box.<strong>theatreB</strong>.<strong>seatsSold</strong>));

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Patron 5 buys ticket for The Giggling Giraffe”</strong>);         box.<strong>sellTicket</strong>(p5, <strong>“The Giggling Giraffe”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Patrons 6 and 9 buy tickets to see Geostorm”</strong>);         box.<strong>sellTicket</strong>(p6, <strong>“Geostorm”</strong>);         box.<strong>sellTicket</strong>(p9, <strong>“Geostorm”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Patrons 7,8,10 buy tickets for Justice League”</strong>);         box.<strong>sellTicket</strong>(p7, <strong>“Justice League”</strong>);         box.<strong>sellTicket</strong>(p8, <strong>“Justice League”</strong>);         box.<strong>sellTicket</strong>(p10, <strong>“Justice League”</strong>);




System.<strong><em>out</em></strong>.println(<strong>“Patron 11 tries to buy tickets for Geostorm”</strong>);         box.<strong>sellTicket</strong>(p11, <strong>“Geostorm”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Geostorm sold out ? ” </strong>+ box.<strong>theatreB</strong>.<strong>isFull</strong>());         System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Patrons 2, 6 and 10 return tickets”</strong>);         box.<strong>returnTicket</strong>(p2);         box.<strong>returnTicket</strong>(p6);         box.<strong>returnTicket</strong>(p10);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Patron 10 tries to return a ticket again”</strong>);         box.<strong>returnTicket</strong>(p10);

System.<strong><em>out</em></strong>.println(<strong>“Geostorm sold out ? ” </strong>+ box.<strong>theatreB</strong>.<strong>isFull</strong>());

System.<strong><em>out</em></strong>.println(<strong>“Geostorm seats remaining: ” </strong>


(box.<strong>theatreB</strong>.<strong>capacity </strong>– box.<strong>theatreB</strong>.<strong>seatsSold</strong>));

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Patrons 11 and 12 buy tickets for Geostorm”</strong>);         box.<strong>sellTicket</strong>(p11, <strong>“Geostorm”</strong>);         box.<strong>sellTicket</strong>(p12, <strong>“Geostorm”</strong>);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Best movie title:    ” </strong>+ box.<strong>bestMovie</strong>().<strong>title</strong>);         System.<strong><em>out</em></strong>.println(<strong>“Best movie earnings: ” </strong>+ box.<strong>bestMovie</strong>().<strong>earnings</strong>);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Theatre A opens movie:  Despicable Me 3″</strong>);         box.<strong>openMovie</strong>(<strong>“Despicable Me 3”</strong>, box.<strong>theatreA</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Patrons 1,2,7,8,12 buy tickets for Despicable Me 3”</strong>);         box.<strong>sellTicket</strong>(p1, <strong>“Despicable Me 3”</strong>);         box.<strong>sellTicket</strong>(p2, <strong>“Despicable Me 3”</strong>);         box.<strong>sellTicket</strong>(p7, <strong>“Despicable Me 3”</strong>);         box.<strong>sellTicket</strong>(p8, <strong>“Despicable Me 3”</strong>);         box.<strong>sellTicket</strong>(p12, <strong>“Despicable Me 3”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Best movie title:    ” </strong>+ box.<strong>bestMovie</strong>().<strong>title</strong>);         System.<strong><em>out</em></strong>.println(<strong>“Best movie earnings: ” </strong>+ box.<strong>bestMovie</strong>().<strong>earnings</strong>);

}

}







Here is the expected output (make sure that your code works before you continue):




Theatre A opens movie: Justice League

Theatre B opens movie: Geostorm

Patron 1 buys ticket to see Justice League

Patrons 2,3 and 4 buy tickets to see Geostorm

Geostorm seats remaining: <strong>2</strong>




Patron 5 buys ticket to see The Giggling Giraffe

<h3>Movie is not currently playing</h3>




Patrons 6 and 9 buy tickets to see Geostorm

Patrons 7, 8 and 10 buy tickets to see Justice League

Patron 11 tries to buy tickets to see Geostorm

<h3>Movie is sold out</h3>

Geostorm sold out ? <strong>true</strong>




Patrons 2, 6 and 10 return tickets




Patron 10 tries to return a ticket again

<h3>Patron does not have a ticket</h3>

Geostorm sold out ? <strong>false</strong>

Geostorm seats remaining: <strong>2</strong>




Patrons 11 and 12 buy tickets to see Geostorm




Best movie title:    <strong>Geostorm</strong> Best movie earnings: <strong>49.5</strong>




Theatre A opens movie:  Despicable Me 3

Patrons 1,2,7,8 &amp; 12 buy tickets to see Despicable Me 3




Best movie title:    <strong>Despicable Me 3</strong>

Best movie earnings: <strong>62.5</strong>


