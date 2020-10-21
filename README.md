# BTM_runner

This is a Python package to run the BTM (Biterm Topic Model) on json data of Twitter, Instagram, Tumblr, Youtube and Reddit

The original C++ code for BTM is here https://github.com/xiaohuiyan/BTM

Please see this reference if you want to know the details of BTM:
Yan, X., Guo, J., Lan, Y., & Cheng, X. (2013, May). A biterm topic model for short texts. In Proceedings of the 22nd international conference on World Wide Web (pp. 1445-1456).

### Please construct your system before run this package
- Install python3 in your system
- Install C++ BTM code list above, put them in folder BTM_master (you can name the fodler whatever you want, but please change the BTM path name in the analyze_data.py file)
- Configure the C++ file in ./BTM_master/src/ using make, get the btm excute file
- Install nltk package

### Then download the BTM_runner package and run the following command

$ python3 analyze_data.py vocab /local/path/to/vocab.txt /local/path/to/index.txt /your/path/to/json_data/ platform

-This command will help us build a vocabulary dictionary for each word based on the text we have in the json file, the vocabulary wil be written to /local/path/to/vocab.txt, and then it will do teh word embedding for each text and put the vector in /local/path/to/index.txt

/your/path/to/json_data/ is a folder used to store the json data for different platforms

platform: This is used specify which platform we are running BTM for, currently it has option:
- youtube_comment, instagram_comment,tumblr_comment,reddit_comment
- youtube_title,youtube_description,instagram_post,twitter,tumblr_post,tumblr_description,reddit_description,reddit_title
Each option specify the text part we want to analyze, comment option will run all the comment under each post

$ python3 analyze_data.py BTM /local/path/to/vocab.txt /local/path/to/index.txt /local/path/to/BTM_result/ k
-This command will help us generate the BTM_result from BTM and write that to /local/path/to/BTM_result/, k is the number of topics we selected

$ python3 write_topicDisplay.py /local/path/to/ BTM_result k /local/path/to/vocab.txt
-This function will write the result of top 30 keywords for each topic under the /local/path/to/BTM_result_topic.txt

#### The BTM_result_topic basically lookslike below
K:20, n(W):993113
p(z)		Top words
0.035260 info:0.156748 bombard:0.048783 retweet:0.048356 today:0.044029 see:0.043897 sorry:0.043641 feed:0.043624 receive:0.043379 auto:0.043356 vital:0.042045 repost:0.038995 enough:0.037427 makes:0.037051 cdc:0.035380 reposted:0.034662 update:0.032969 retweeted:0.032564 get:0.031378 times:0.005541 doomsday:0.005239 ten:0.005177 extending:0.005125 politicians:0.004954 cover:0.004937 asses:0.004891 lockdowns:0.004880 gadkari:0.004709 media:0.004681 least:0.004458 time:0.004333
0.027883 delhi:0.018361 pandemic:0.018155 govt:0.017154 oxy:0.013013 happy:0.010342 say:0.009873 hospital:0.009397 support:0.009362 every:0.009014 better:0.008779 thanks:0.008737 love:0.008261 day:0.008225 guys:0.008090 thank:0.007962 hard:0.007863 single:0.007728 stronger:0.007444 neo:0.007302 struggle:0.007195 gotta:0.006904 gettin:0.006833 efforts:0.006577 covid:0.006549 nazi:0.006513 patients:0.006499 goodfellas:0.006371 mend:0.006350 god:0.006307 fight:0.006066
0.024451 covid:0.019642 morph:0.017645 19:0.014830 dr:0.012536 new:0.010170 last:0.008927 normal:0.008831 also:0.007796 device:0.007772 know:0.007315 5:0.006777 yrs:0.006248 end:0.005935 face:0.005911 oxy:0.005735 sir:0.005703 beginning:0.005302 disease:0.005085 death:0.004941 still:0.004692 murder:0.004532 future:0.004451 uk:0.004451 use:0.004435 great:0.004363 science:0.004195 disruption:0.004050 immunity:0.003770 frm:0.003730 talk:0.003714
0.022656 trump:0.054731 bombshell:0.029976 covid:0.027895 official:0.026665 cdc:0.022579 reports:0.021194 19:0.019998 corona:0.015638 former:0.013719 michael:0.013582 caputo:0.013547 defeat:0.013444 campaign:0.013401 percs:0.013401 ay:0.013315 allegations:0.013238 politico:0.013005 march:0.012395 downplaying:0.012378 according:0.012085 right:0.011672 scientific:0.011535 spokesperson:0.011380 demanded:0.010898 change:0.010700 china:0.010158 review:0.010141 weekly:0.009427 interfered:0.008670 officials:0.007974
0.029108 oxy:0.035554 oximeters:0.023823 covid:0.023748 oxygen:0.023591 check:0.023325 levels:0.022711 state:0.015368 used:0.015204 assam:0.014037 requested:0.013655 units:0.012318 campaign:0.012277 volunteers:0.012249 guwahati:0.012181 panchayat:0.011601 care:0.011369 focus:0.011144 gaon:0.011021 90:0.010946 sonapur:0.010441 mitra:0.010352 launched:0.009991 95:0.008987 respective:0.008701 areas:0.008305 pulse:0.007377 thing:0.006981 94:0.006892 u:0.006271 hospital:0.006190
0.038675 like:0.057752 xanax:0.044374 doctors:0.033959 give:0.032997 literally:0.032297 oxycontin:0.032094 pandemic:0.032057 candy:0.031812 addiction:0.029728 fact:0.029649 recovery:0.028239 drug:0.028197 programs:0.026928 opiate:0.025496 ridiculously:0.025308 national:0.024331 expensive:0.024243 even:0.023365 cause:0.023271 insurance:0.021589 root:0.021474 yes:0.020691 edm:0.019980 music:0.019181 ahhh:0.018685 g6:0.015744 someone:0.007919 feelin:0.007835 fly:0.007658 washing:0.006498
0.363336 covid:0.030279 pandemic:0.010209 morph:0.009505 19:0.008052 xanax:0.007118 like:0.006925 people:0.006879 get:0.006302 bomb:0.005208 pain:0.005086 oxy:0.004554 one:0.004549 us:0.004409 take:0.004279 would:0.004226 going:0.004142 go:0.003885 trump:0.003796 need:0.003670 time:0.003343 know:0.003178 virus:0.003172 corona:0.003154 back:0.003082 even:0.002952 2:0.002884 killers:0.002790 year:0.002783 due:0.002772 think:0.002725
0.070326 bomb:0.038952 covid:0.025237 us:0.014571 world:0.011383 plan:0.010127 trump:0.009327 people:0.009000 country:0.008903 pandemic:0.007753 coronavirus:0.007595 save:0.006459 americans:0.006374 000:0.006186 19:0.005665 deaths:0.005297 get:0.005141 bad:0.004977 lives:0.004641 morph:0.004586 virus:0.004521 order:0.004406 pay:0.004312 china:0.004230 bill:0.004038 3000:0.003968 bombs:0.003941 got:0.003797 ago:0.003621 fight:0.003606 center:0.003562
0.023135 bomb:0.056158 coronavirus:0.032404 china:0.022843 gaza:0.020801 middle:0.020320 mulan:0.016835 israel:0.016202 pandemic:0.016050 likely:0.014658 film:0.014126 controversy:0.013367 regardless:0.013054 hit:0.012869 continuing:0.012430 fails:0.012430 inspire:0.012253 audiences:0.012118 yifei:0.012092 liu:0.012084 life:0.011957 boycotts:0.011881 infections:0.011367 unprecedented:0.011232 number:0.011189 suffering:0.010844 unexpected:0.010776 besieged:0.010717 shut:0.010649 global:0.009603 via:0.008852
0.026303 briefings:0.076973 pandemic:0.066701 one:0.066529 bombs:0.064992 photo:0.064377 case:0.062525 greatest:0.062345 era:0.062105 missed:0.061790 irwinredlenermd:0.061475 grandson:0.061475 declas:0.038239 hope:0.036687 morph:0.035698 covid:0.034978 levies:0.003479 taxpayers:0.003224 anybody:0.003074 scheme:0.003074 determine:0.002939 upon:0.002917 tax:0.002692 political:0.002654 period:0.002564 based:0.002414 vote:0.002287 normal:0.002129 way:0.001830 life:0.001800 change:0.001755
0.034119 gaza:0.078423 electricity:0.046127 water:0.043504 day:0.034807 4:0.034689 living:0.034548 woke:0.034148 less:0.033901 hours:0.033772 morning:0.032649 undrinkable:0.031861 bombs:0.031778 devastating:0.028885 97:0.028850 covid:0.027832 youth:0.027421 could:0.027015 r:0.024857 majority:0.024587 thinking:0.023716 sleep:0.021670 rubble:0.021240 virus:0.015372 israel:0.014989 outbreak:0.014249 continues:0.013608 corona:0.013078 humanitarian:0.013025 disaster:0.011279 tell:0.010914
0.017400 along:0.034393 supposed:0.032242 go:0.032187 accept:0.032024 blindly:0.031183 ask:0.030495 propaganda:0.030211 piece:0.029589 message:0.028999 questions:0.028912 another:0.027907 sync:0.027427 msm:0.027383 yes:0.026073 w:0.025735 morph:0.025429 covid:0.024337 pow:0.022088 named:0.021837 corona:0.021094 sheep:0.020974 believe:0.020614 virus:0.019948 finished:0.018376 f:0.018070 mission:0.007708 mercy:0.006125 pandemic:0.004302 experts:0.003581 million:0.003287
0.023081 pain:0.043728 fucking:0.040667 killers:0.035433 covid:0.034198 take:0.031712 children:0.030832 without:0.028371 gave:0.027898 graham:0.027517 birth:0.027433 four:0.027340 painless:0.027095 lindsey:0.027086 hospitals:0.010351 incompetence:0.010325 policy:0.009987 full:0.009615 already:0.009133 limited:0.008981 even:0.008896 supplies:0.008634 evil:0.008516 global:0.008448 cowards:0.008177 pandemic:0.008000 question:0.007856 murderers:0.007729 armenia:0.007704 civilians:0.007577 colonizers:0.007306
0.025005 football:0.021307 covid:0.020718 oxy:0.018942 pandemic:0.017284 program:0.014975 morph:0.013521 indian:0.012555 help:0.012311 19:0.010214 occidental:0.010135 financial:0.009609 challenges:0.009412 trump:0.009294 specific:0.009161 substantial:0.009145 trying:0.008744 losing:0.008595 us:0.008579 comes:0.008446 impacts:0.008320 control:0.008281 mental:0.008147 fly:0.008061 today:0.007959 normal:0.007935 situation:0.007904 alot:0.007896 pressure:0.007833 giant:0.007778 reflecting:0.007354
0.038140 bomb:0.029450 lockdown:0.024792 covid:0.023543 beds:0.020098 palestinians:0.018361 week:0.015958 f:0.015779 oxy:0.014958 pandemic:0.014360 double:0.013068 law:0.013037 measures:0.012973 reinstated:0.012947 causing:0.012904 suffer:0.012889 continues:0.012661 israel:0.012216 anti:0.012089 regardless:0.011936 members:0.011893 bombard:0.011862 pushing:0.011729 cities:0.011650 campaign:0.011475 protests:0.011380 weekend:0.011317 state:0.011168 120k:0.010671 surely:0.010321 planning:0.010311
0.009105 numbers:0.029739 covid:0.028675 inside:0.028200 trump:0.023852 admin:0.023035 data:0.022503 sources:0.021763 bombshell:0.021687 cdc:0.021345 hello:0.021079 confirm:0.020832 inflate:0.020737 misreporting:0.020718 via:0.010768 among:0.008926 patients:0.008337 use:0.006666 substance:0.005109 india:0.005090 disorder:0.004900 diagnosed:0.004729 6:0.004710 higher:0.004425 risk:0.004273 far:0.004273 begs:0.004254 19:0.004216 good:0.004178 bomb:0.004102 pussy:0.004064
0.121037 reed:0.045230 sign:0.043652 walter:0.043603 mental:0.042323 fleeing:0.042067 brought:0.040781 breakdown:0.040361 resources:0.038892 need:0.038868 hospital:0.037363 hear:0.037207 morph:0.035837 docs:0.035513 alf:0.035513 lie:0.033965 covid:0.033918 wh:0.032581 infection:0.030747 hospitalized:0.030738 needs:0.029660 go:0.029357 air:0.027594 joy:0.027499 ride:0.025932 gasping:0.025828 zero:0.024369 mask:0.024234 patient:0.022762 removal:0.022610 karen:0.000100
0.024890 covid:0.040854 000:0.036467 deaths:0.033753 bad:0.029524 run:0.024964 need:0.022818 192:0.019528 get:0.017232 3:0.017129 teary:0.017011 eyed:0.017011 mouth:0.016309 used:0.015441 people:0.015330 years:0.015046 fucking:0.014762 permission:0.014636 cha:0.014581 slip:0.013918 take:0.013452 seriously:0.013413 bomb:0.012924 20:0.012585 died:0.011914 taking:0.011346 ignore:0.011022 americans:0.010746 coronavirus:0.010454 got:0.009949 dead:0.009918
0.020156 covid:0.044497 morph:0.035762 country:0.022894 free:0.022550 shown:0.022349 quickly:0.021641 nazi:0.021373 grew:0.021019 germany:0.020962 tory:0.020885 lived:0.020837 thinking:0.020789 govnt:0.020665 soviet:0.020665 union:0.020588 generation:0.020244 relief:0.019833 lockdowns:0.018713 19:0.011815 states:0.011328 news:0.011222 climate:0.010974 blue:0.010620 instructs:0.010246 talks:0.010141 measure:0.010017 staff:0.009998 predicated:0.009644 kills:0.009615 first:0.009567
0.025932 police:0.031907 mask:0.029218 bomb:0.027820 people:0.027402 country:0.027197 secret:0.025526 kidnapping:0.023307 wear:0.023102 want:0.022692 like:0.022669 need:0.022510 feel:0.022502 pandemic:0.022479 running:0.020451 protesters:0.018916 putin:0.018233 economy:0.018126 hurts:0.017184 puts:0.017108 bounty:0.016174 kids:0.015999 troops:0.015589 except:0.015475 pro:0.015239 life:0.014761 shot:0.013948 school:0.013621 republicans:0.012459 set:0.008357 therapies:0.008038