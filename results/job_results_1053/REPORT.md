---
title: "Risk Factor Analysis"
output: 
  html_document:
    keep_md: TRUE
    self_contained: true
required_packages:  ['github://HBGD-UCB/longbowRiskFactors','github://jeremyrcoyle/skimr@vector_types', 'github://tlverse/delayed']
params:
  roles:
    value:
      - exclude
      - strata
      - id
      - W
      - A
      - Y
  data: 
    value: 
      type: 'web'
      uri: 'https://raw.githubusercontent.com/HBGD-UCB/longbowRiskFactors/master/inst/sample_data/birthwt_data.rdata'
  nodes:
    value:
      strata: ['study_id', 'mrace']
      id: ['subjid']
      W: []
      A: ['parity_cat']
      Y: ['haz01']
  script_params:
    value:
      parallelize:
        input: checkbox
        value: FALSE
      baseline_level:
        input: 'character'
        value: "[1,2)"
  output_directory:
    value: ''

---







## Methods
## Outcome Variable

**Outcome Variable:** sstunted

## Predictor Variables

**Intervention Variable:** birthwt

**Adjustment Set:**

unadjusted

## Stratifying Variables

The analysis was stratified on these variable(s):

* agecat
* studyid
* country

## Data Summary

agecat      studyid                    country                        A              n     nA   nAY0   nAY1
----------  -------------------------  -----------------------------  --------  ------  -----  -----  -----
Birth       ki0047075b-MAL-ED          BANGLADESH                     >=0          257     34     34      0
Birth       ki0047075b-MAL-ED          BANGLADESH                     <-3          257      7      2      5
Birth       ki0047075b-MAL-ED          BANGLADESH                     [-3--2)      257     38     35      3
Birth       ki0047075b-MAL-ED          BANGLADESH                     [-2--1)      257     96     95      1
Birth       ki0047075b-MAL-ED          BANGLADESH                     [-1-0)       257     82     82      0
Birth       ki0047075b-MAL-ED          BRAZIL                         >=0          191    111    110      1
Birth       ki0047075b-MAL-ED          BRAZIL                         <-3          191      0      0      0
Birth       ki0047075b-MAL-ED          BRAZIL                         [-3--2)      191      6      3      3
Birth       ki0047075b-MAL-ED          BRAZIL                         [-2--1)      191     19     16      3
Birth       ki0047075b-MAL-ED          BRAZIL                         [-1-0)       191     55     54      1
Birth       ki0047075b-MAL-ED          INDIA                          >=0          206     40     40      0
Birth       ki0047075b-MAL-ED          INDIA                          <-3          206      2      0      2
Birth       ki0047075b-MAL-ED          INDIA                          [-3--2)      206     21     20      1
Birth       ki0047075b-MAL-ED          INDIA                          [-2--1)      206     68     65      3
Birth       ki0047075b-MAL-ED          INDIA                          [-1-0)       206     75     74      1
Birth       ki0047075b-MAL-ED          NEPAL                          >=0          173     32     32      0
Birth       ki0047075b-MAL-ED          NEPAL                          <-3          173      4      1      3
Birth       ki0047075b-MAL-ED          NEPAL                          [-3--2)      173     12     10      2
Birth       ki0047075b-MAL-ED          NEPAL                          [-2--1)      173     40     39      1
Birth       ki0047075b-MAL-ED          NEPAL                          [-1-0)       173     85     85      0
Birth       ki0047075b-MAL-ED          PERU                           >=0          287     90     90      0
Birth       ki0047075b-MAL-ED          PERU                           <-3          287      4      1      3
Birth       ki0047075b-MAL-ED          PERU                           [-3--2)      287      9      7      2
Birth       ki0047075b-MAL-ED          PERU                           [-2--1)      287     42     39      3
Birth       ki0047075b-MAL-ED          PERU                           [-1-0)       287    142    142      0
Birth       ki0047075b-MAL-ED          SOUTH AFRICA                   >=0          262     91     91      0
Birth       ki0047075b-MAL-ED          SOUTH AFRICA                   <-3          262      5      4      1
Birth       ki0047075b-MAL-ED          SOUTH AFRICA                   [-3--2)      262     11     10      1
Birth       ki0047075b-MAL-ED          SOUTH AFRICA                   [-2--1)      262     39     39      0
Birth       ki0047075b-MAL-ED          SOUTH AFRICA                   [-1-0)       262    116    116      0
Birth       ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   >=0          123     55     54      1
Birth       ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   <-3          123      1      0      1
Birth       ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-3--2)      123      5      3      2
Birth       ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-2--1)      123     17     16      1
Birth       ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-1-0)       123     45     44      1
Birth       ki1000108-CMC-V-BCS-2002   INDIA                          >=0           90     11     11      0
Birth       ki1000108-CMC-V-BCS-2002   INDIA                          <-3           90      2      2      0
Birth       ki1000108-CMC-V-BCS-2002   INDIA                          [-3--2)       90      8      8      0
Birth       ki1000108-CMC-V-BCS-2002   INDIA                          [-2--1)       90     32     30      2
Birth       ki1000108-CMC-V-BCS-2002   INDIA                          [-1-0)        90     37     36      1
Birth       ki1000108-IRC              INDIA                          >=0          383     58     57      1
Birth       ki1000108-IRC              INDIA                          <-3          383     12      9      3
Birth       ki1000108-IRC              INDIA                          [-3--2)      383     39     37      2
Birth       ki1000108-IRC              INDIA                          [-2--1)      383    124    118      6
Birth       ki1000108-IRC              INDIA                          [-1-0)       383    150    146      4
Birth       ki1000109-EE               PAKISTAN                       >=0            2      0      0      0
Birth       ki1000109-EE               PAKISTAN                       <-3            2      0      0      0
Birth       ki1000109-EE               PAKISTAN                       [-3--2)        2      0      0      0
Birth       ki1000109-EE               PAKISTAN                       [-2--1)        2      2      2      0
Birth       ki1000109-EE               PAKISTAN                       [-1-0)         2      0      0      0
Birth       ki1000109-ResPak           PAKISTAN                       >=0            7      4      4      0
Birth       ki1000109-ResPak           PAKISTAN                       <-3            7      1      1      0
Birth       ki1000109-ResPak           PAKISTAN                       [-3--2)        7      0      0      0
Birth       ki1000109-ResPak           PAKISTAN                       [-2--1)        7      1      1      0
Birth       ki1000109-ResPak           PAKISTAN                       [-1-0)         7      1      1      0
Birth       ki1017093-NIH-Birth        BANGLADESH                     >=0           28      2      2      0
Birth       ki1017093-NIH-Birth        BANGLADESH                     <-3           28      0      0      0
Birth       ki1017093-NIH-Birth        BANGLADESH                     [-3--2)       28      4      4      0
Birth       ki1017093-NIH-Birth        BANGLADESH                     [-2--1)       28     15     15      0
Birth       ki1017093-NIH-Birth        BANGLADESH                     [-1-0)        28      7      7      0
Birth       ki1017093c-NIH-Crypto      BANGLADESH                     >=0           27      1      1      0
Birth       ki1017093c-NIH-Crypto      BANGLADESH                     <-3           27      0      0      0
Birth       ki1017093c-NIH-Crypto      BANGLADESH                     [-3--2)       27      7      7      0
Birth       ki1017093c-NIH-Crypto      BANGLADESH                     [-2--1)       27      9      8      1
Birth       ki1017093c-NIH-Crypto      BANGLADESH                     [-1-0)        27     10     10      0
Birth       ki1101329-Keneba           GAMBIA                         >=0         1541    288    287      1
Birth       ki1101329-Keneba           GAMBIA                         <-3         1541     18     12      6
Birth       ki1101329-Keneba           GAMBIA                         [-3--2)     1541     95     92      3
Birth       ki1101329-Keneba           GAMBIA                         [-2--1)     1541    435    424     11
Birth       ki1101329-Keneba           GAMBIA                         [-1-0)      1541    705    697      8
Birth       ki1114097-CMIN             BANGLADESH                     >=0           12      2      2      0
Birth       ki1114097-CMIN             BANGLADESH                     <-3           12      3      1      2
Birth       ki1114097-CMIN             BANGLADESH                     [-3--2)       12      3      1      2
Birth       ki1114097-CMIN             BANGLADESH                     [-2--1)       12      1      1      0
Birth       ki1114097-CMIN             BANGLADESH                     [-1-0)        12      3      3      0
Birth       ki1114097-CMIN             BRAZIL                         >=0          115     56     56      0
Birth       ki1114097-CMIN             BRAZIL                         <-3          115      1      0      1
Birth       ki1114097-CMIN             BRAZIL                         [-3--2)      115      2      1      1
Birth       ki1114097-CMIN             BRAZIL                         [-2--1)      115     18     17      1
Birth       ki1114097-CMIN             BRAZIL                         [-1-0)       115     38     38      0
Birth       ki1114097-CMIN             PERU                           >=0           10      8      8      0
Birth       ki1114097-CMIN             PERU                           <-3           10      0      0      0
Birth       ki1114097-CMIN             PERU                           [-3--2)       10      0      0      0
Birth       ki1114097-CMIN             PERU                           [-2--1)       10      0      0      0
Birth       ki1114097-CMIN             PERU                           [-1-0)        10      2      2      0
Birth       ki1114097-CONTENT          PERU                           >=0            2      1      1      0
Birth       ki1114097-CONTENT          PERU                           <-3            2      0      0      0
Birth       ki1114097-CONTENT          PERU                           [-3--2)        2      0      0      0
Birth       ki1114097-CONTENT          PERU                           [-2--1)        2      0      0      0
Birth       ki1114097-CONTENT          PERU                           [-1-0)         2      1      1      0
Birth       ki1126311-ZVITAMBO         ZIMBABWE                       >=0        13830   3171   3162      9
Birth       ki1126311-ZVITAMBO         ZIMBABWE                       <-3        13830    404    264    140
Birth       ki1126311-ZVITAMBO         ZIMBABWE                       [-3--2)    13830   1172   1021    151
Birth       ki1126311-ZVITAMBO         ZIMBABWE                       [-2--1)    13830   3345   3245    100
Birth       ki1126311-ZVITAMBO         ZIMBABWE                       [-1-0)     13830   5738   5697     41
Birth       ki1135781-COHORTS          GUATEMALA                      >=0          383    103    103      0
Birth       ki1135781-COHORTS          GUATEMALA                      <-3          383      5      2      3
Birth       ki1135781-COHORTS          GUATEMALA                      [-3--2)      383     38     38      0
Birth       ki1135781-COHORTS          GUATEMALA                      [-2--1)      383    113    113      0
Birth       ki1135781-COHORTS          GUATEMALA                      [-1-0)       383    124    124      0
Birth       ki1135781-COHORTS          INDIA                          >=0         6637    760    758      2
Birth       ki1135781-COHORTS          INDIA                          <-3         6637    284    162    122
Birth       ki1135781-COHORTS          INDIA                          [-3--2)     6637    861    808     53
Birth       ki1135781-COHORTS          INDIA                          [-2--1)     6637   2256   2236     20
Birth       ki1135781-COHORTS          INDIA                          [-1-0)      6637   2476   2468      8
Birth       ki1135781-COHORTS          PHILIPPINES                    >=0         3002    654    654      0
Birth       ki1135781-COHORTS          PHILIPPINES                    <-3         3002     71     46     25
Birth       ki1135781-COHORTS          PHILIPPINES                    [-3--2)     3002    177    165     12
Birth       ki1135781-COHORTS          PHILIPPINES                    [-2--1)     3002    720    716      4
Birth       ki1135781-COHORTS          PHILIPPINES                    [-1-0)      3002   1380   1378      2
3 months    ki0047075b-MAL-ED          BANGLADESH                     >=0          243     33     33      0
3 months    ki0047075b-MAL-ED          BANGLADESH                     <-3          243      4      3      1
3 months    ki0047075b-MAL-ED          BANGLADESH                     [-3--2)      243     35     31      4
3 months    ki0047075b-MAL-ED          BANGLADESH                     [-2--1)      243     92     90      2
3 months    ki0047075b-MAL-ED          BANGLADESH                     [-1-0)       243     79     79      0
3 months    ki0047075b-MAL-ED          BRAZIL                         >=0          225    126    126      0
3 months    ki0047075b-MAL-ED          BRAZIL                         <-3          225      0      0      0
3 months    ki0047075b-MAL-ED          BRAZIL                         [-3--2)      225      9      8      1
3 months    ki0047075b-MAL-ED          BRAZIL                         [-2--1)      225     22     22      0
3 months    ki0047075b-MAL-ED          BRAZIL                         [-1-0)       225     68     68      0
3 months    ki0047075b-MAL-ED          INDIA                          >=0          235     43     43      0
3 months    ki0047075b-MAL-ED          INDIA                          <-3          235      5      2      3
3 months    ki0047075b-MAL-ED          INDIA                          [-3--2)      235     23     21      2
3 months    ki0047075b-MAL-ED          INDIA                          [-2--1)      235     76     70      6
3 months    ki0047075b-MAL-ED          INDIA                          [-1-0)       235     88     87      1
3 months    ki0047075b-MAL-ED          NEPAL                          >=0          229     47     47      0
3 months    ki0047075b-MAL-ED          NEPAL                          <-3          229      4      3      1
3 months    ki0047075b-MAL-ED          NEPAL                          [-3--2)      229     15     14      1
3 months    ki0047075b-MAL-ED          NEPAL                          [-2--1)      229     53     52      1
3 months    ki0047075b-MAL-ED          NEPAL                          [-1-0)       229    110    110      0
3 months    ki0047075b-MAL-ED          PERU                           >=0          288     91     90      1
3 months    ki0047075b-MAL-ED          PERU                           <-3          288      4      1      3
3 months    ki0047075b-MAL-ED          PERU                           [-3--2)      288     10      5      5
3 months    ki0047075b-MAL-ED          PERU                           [-2--1)      288     42     33      9
3 months    ki0047075b-MAL-ED          PERU                           [-1-0)       288    141    139      2
3 months    ki0047075b-MAL-ED          SOUTH AFRICA                   >=0          281    106    106      0
3 months    ki0047075b-MAL-ED          SOUTH AFRICA                   <-3          281      4      4      0
3 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-3--2)      281     12      8      4
3 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-2--1)      281     42     39      3
3 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-1-0)       281    117    114      3
3 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   >=0          127     58     58      0
3 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   <-3          127      0      0      0
3 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-3--2)      127      5      2      3
3 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-2--1)      127     17     16      1
3 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-1-0)       127     47     46      1
3 months    ki1000108-CMC-V-BCS-2002   INDIA                          >=0          355     68     66      2
3 months    ki1000108-CMC-V-BCS-2002   INDIA                          <-3          355     12      8      4
3 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-3--2)      355     29     19     10
3 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-2--1)      355    105     95     10
3 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-1-0)       355    141    134      7
3 months    ki1000108-IRC              INDIA                          >=0          401     60     59      1
3 months    ki1000108-IRC              INDIA                          <-3          401     13      8      5
3 months    ki1000108-IRC              INDIA                          [-3--2)      401     41     31     10
3 months    ki1000108-IRC              INDIA                          [-2--1)      401    133    120     13
3 months    ki1000108-IRC              INDIA                          [-1-0)       401    154    149      5
3 months    ki1000109-EE               PAKISTAN                       >=0          373     34     33      1
3 months    ki1000109-EE               PAKISTAN                       <-3          373     46     15     31
3 months    ki1000109-EE               PAKISTAN                       [-3--2)      373     73     33     40
3 months    ki1000109-EE               PAKISTAN                       [-2--1)      373    118     84     34
3 months    ki1000109-EE               PAKISTAN                       [-1-0)       373    102     89     13
3 months    ki1000109-ResPak           PAKISTAN                       >=0            6      3      3      0
3 months    ki1000109-ResPak           PAKISTAN                       <-3            6      1      1      0
3 months    ki1000109-ResPak           PAKISTAN                       [-3--2)        6      0      0      0
3 months    ki1000109-ResPak           PAKISTAN                       [-2--1)        6      1      0      1
3 months    ki1000109-ResPak           PAKISTAN                       [-1-0)         6      1      1      0
3 months    ki1017093-NIH-Birth        BANGLADESH                     >=0           23      1      1      0
3 months    ki1017093-NIH-Birth        BANGLADESH                     <-3           23      0      0      0
3 months    ki1017093-NIH-Birth        BANGLADESH                     [-3--2)       23      3      3      0
3 months    ki1017093-NIH-Birth        BANGLADESH                     [-2--1)       23     12     12      0
3 months    ki1017093-NIH-Birth        BANGLADESH                     [-1-0)        23      7      7      0
3 months    ki1017093b-PROVIDE         BANGLADESH                     >=0          645     59     59      0
3 months    ki1017093b-PROVIDE         BANGLADESH                     <-3          645      4      3      1
3 months    ki1017093b-PROVIDE         BANGLADESH                     [-3--2)      645    105     97      8
3 months    ki1017093b-PROVIDE         BANGLADESH                     [-2--1)      645    271    271      0
3 months    ki1017093b-PROVIDE         BANGLADESH                     [-1-0)       645    206    205      1
3 months    ki1017093c-NIH-Crypto      BANGLADESH                     >=0          728     96     96      0
3 months    ki1017093c-NIH-Crypto      BANGLADESH                     <-3          728     23     17      6
3 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-3--2)      728    109     94     15
3 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-2--1)      728    274    264     10
3 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-1-0)       728    226    224      2
3 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   >=0         2266    983    980      3
3 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   <-3         2266     21     15      6
3 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-3--2)     2266     45     42      3
3 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-2--1)     2266    293    286      7
3 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-1-0)      2266    924    919      5
3 months    ki1101329-Keneba           GAMBIA                         >=0         1803    360    360      0
3 months    ki1101329-Keneba           GAMBIA                         <-3         1803     24     16      8
3 months    ki1101329-Keneba           GAMBIA                         [-3--2)     1803    111     92     19
3 months    ki1101329-Keneba           GAMBIA                         [-2--1)     1803    505    489     16
3 months    ki1101329-Keneba           GAMBIA                         [-1-0)      1803    803    794      9
3 months    ki1114097-CMIN             BRAZIL                         >=0           88     40     40      0
3 months    ki1114097-CMIN             BRAZIL                         <-3           88      1      1      0
3 months    ki1114097-CMIN             BRAZIL                         [-3--2)       88      2      2      0
3 months    ki1114097-CMIN             BRAZIL                         [-2--1)       88     13     11      2
3 months    ki1114097-CMIN             BRAZIL                         [-1-0)        88     32     31      1
3 months    ki1114097-CMIN             PERU                           >=0            9      8      8      0
3 months    ki1114097-CMIN             PERU                           <-3            9      0      0      0
3 months    ki1114097-CMIN             PERU                           [-3--2)        9      0      0      0
3 months    ki1114097-CMIN             PERU                           [-2--1)        9      0      0      0
3 months    ki1114097-CMIN             PERU                           [-1-0)         9      1      1      0
3 months    ki1114097-CONTENT          PERU                           >=0            2      1      1      0
3 months    ki1114097-CONTENT          PERU                           <-3            2      0      0      0
3 months    ki1114097-CONTENT          PERU                           [-3--2)        2      0      0      0
3 months    ki1114097-CONTENT          PERU                           [-2--1)        2      0      0      0
3 months    ki1114097-CONTENT          PERU                           [-1-0)         2      1      1      0
3 months    ki1126311-ZVITAMBO         ZIMBABWE                       >=0         9163   2163   2141     22
3 months    ki1126311-ZVITAMBO         ZIMBABWE                       <-3         9163    243    109    134
3 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-3--2)     9163    720    599    121
3 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-2--1)     9163   2192   2054    138
3 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-1-0)      9163   3845   3736    109
3 months    ki1135781-COHORTS          GUATEMALA                      >=0          405    109    105      4
3 months    ki1135781-COHORTS          GUATEMALA                      <-3          405      6      3      3
3 months    ki1135781-COHORTS          GUATEMALA                      [-3--2)      405     37     23     14
3 months    ki1135781-COHORTS          GUATEMALA                      [-2--1)      405    122    117      5
3 months    ki1135781-COHORTS          GUATEMALA                      [-1-0)       405    131    122      9
3 months    ki1135781-COHORTS          INDIA                          >=0         6463    728    728      0
3 months    ki1135781-COHORTS          INDIA                          <-3         6463    272    163    109
3 months    ki1135781-COHORTS          INDIA                          [-3--2)     6463    845    786     59
3 months    ki1135781-COHORTS          INDIA                          [-2--1)     6463   2199   2149     50
3 months    ki1135781-COHORTS          INDIA                          [-1-0)      6463   2419   2408     11
3 months    ki1135781-COHORTS          PHILIPPINES                    >=0         2831    614    614      0
3 months    ki1135781-COHORTS          PHILIPPINES                    <-3         2831     60     35     25
3 months    ki1135781-COHORTS          PHILIPPINES                    [-3--2)     2831    159    145     14
3 months    ki1135781-COHORTS          PHILIPPINES                    [-2--1)     2831    692    668     24
3 months    ki1135781-COHORTS          PHILIPPINES                    [-1-0)      2831   1306   1296     10
6 months    ki0047075b-MAL-ED          BANGLADESH                     >=0          234     33     33      0
6 months    ki0047075b-MAL-ED          BANGLADESH                     <-3          234      4      4      0
6 months    ki0047075b-MAL-ED          BANGLADESH                     [-3--2)      234     34     29      5
6 months    ki0047075b-MAL-ED          BANGLADESH                     [-2--1)      234     86     84      2
6 months    ki0047075b-MAL-ED          BANGLADESH                     [-1-0)       234     77     76      1
6 months    ki0047075b-MAL-ED          BRAZIL                         >=0          209    120    120      0
6 months    ki0047075b-MAL-ED          BRAZIL                         <-3          209      0      0      0
6 months    ki0047075b-MAL-ED          BRAZIL                         [-3--2)      209      8      8      0
6 months    ki0047075b-MAL-ED          BRAZIL                         [-2--1)      209     21     21      0
6 months    ki0047075b-MAL-ED          BRAZIL                         [-1-0)       209     60     60      0
6 months    ki0047075b-MAL-ED          INDIA                          >=0          231     41     41      0
6 months    ki0047075b-MAL-ED          INDIA                          <-3          231      5      2      3
6 months    ki0047075b-MAL-ED          INDIA                          [-3--2)      231     22     21      1
6 months    ki0047075b-MAL-ED          INDIA                          [-2--1)      231     75     72      3
6 months    ki0047075b-MAL-ED          INDIA                          [-1-0)       231     88     86      2
6 months    ki0047075b-MAL-ED          NEPAL                          >=0          229     48     48      0
6 months    ki0047075b-MAL-ED          NEPAL                          <-3          229      4      3      1
6 months    ki0047075b-MAL-ED          NEPAL                          [-3--2)      229     15     15      0
6 months    ki0047075b-MAL-ED          NEPAL                          [-2--1)      229     53     53      0
6 months    ki0047075b-MAL-ED          NEPAL                          [-1-0)       229    109    109      0
6 months    ki0047075b-MAL-ED          PERU                           >=0          270     83     83      0
6 months    ki0047075b-MAL-ED          PERU                           <-3          270      4      1      3
6 months    ki0047075b-MAL-ED          PERU                           [-3--2)      270      9      6      3
6 months    ki0047075b-MAL-ED          PERU                           [-2--1)      270     40     36      4
6 months    ki0047075b-MAL-ED          PERU                           [-1-0)       270    134    132      2
6 months    ki0047075b-MAL-ED          SOUTH AFRICA                   >=0          254    100    100      0
6 months    ki0047075b-MAL-ED          SOUTH AFRICA                   <-3          254      3      3      0
6 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-3--2)      254     10      7      3
6 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-2--1)      254     37     36      1
6 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-1-0)       254    104    102      2
6 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   >=0          124     55     55      0
6 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   <-3          124      0      0      0
6 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-3--2)      124      5      4      1
6 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-2--1)      124     17     15      2
6 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-1-0)       124     47     45      2
6 months    ki1000108-CMC-V-BCS-2002   INDIA                          >=0          361     69     65      4
6 months    ki1000108-CMC-V-BCS-2002   INDIA                          <-3          361     11      8      3
6 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-3--2)      361     30     21      9
6 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-2--1)      361    105     92     13
6 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-1-0)       361    146    133     13
6 months    ki1000108-IRC              INDIA                          >=0          401     61     59      2
6 months    ki1000108-IRC              INDIA                          <-3          401     11      9      2
6 months    ki1000108-IRC              INDIA                          [-3--2)      401     41     34      7
6 months    ki1000108-IRC              INDIA                          [-2--1)      401    132    119     13
6 months    ki1000108-IRC              INDIA                          [-1-0)       401    156    153      3
6 months    ki1000109-EE               PAKISTAN                       >=0          369     35     31      4
6 months    ki1000109-EE               PAKISTAN                       <-3          369     46     23     23
6 months    ki1000109-EE               PAKISTAN                       [-3--2)      369     69     41     28
6 months    ki1000109-EE               PAKISTAN                       [-2--1)      369    116     90     26
6 months    ki1000109-EE               PAKISTAN                       [-1-0)       369    103     92     11
6 months    ki1000109-ResPak           PAKISTAN                       >=0            5      2      2      0
6 months    ki1000109-ResPak           PAKISTAN                       <-3            5      1      1      0
6 months    ki1000109-ResPak           PAKISTAN                       [-3--2)        5      0      0      0
6 months    ki1000109-ResPak           PAKISTAN                       [-2--1)        5      1      0      1
6 months    ki1000109-ResPak           PAKISTAN                       [-1-0)         5      1      1      0
6 months    ki1017093-NIH-Birth        BANGLADESH                     >=0           17      1      1      0
6 months    ki1017093-NIH-Birth        BANGLADESH                     <-3           17      0      0      0
6 months    ki1017093-NIH-Birth        BANGLADESH                     [-3--2)       17      3      3      0
6 months    ki1017093-NIH-Birth        BANGLADESH                     [-2--1)       17      9      9      0
6 months    ki1017093-NIH-Birth        BANGLADESH                     [-1-0)        17      4      4      0
6 months    ki1017093b-PROVIDE         BANGLADESH                     >=0          583     51     51      0
6 months    ki1017093b-PROVIDE         BANGLADESH                     <-3          583      4      3      1
6 months    ki1017093b-PROVIDE         BANGLADESH                     [-3--2)      583     92     83      9
6 months    ki1017093b-PROVIDE         BANGLADESH                     [-2--1)      583    246    243      3
6 months    ki1017093b-PROVIDE         BANGLADESH                     [-1-0)       583    190    189      1
6 months    ki1017093c-NIH-Crypto      BANGLADESH                     >=0          715     92     92      0
6 months    ki1017093c-NIH-Crypto      BANGLADESH                     <-3          715     22     17      5
6 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-3--2)      715    108    101      7
6 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-2--1)      715    271    263      8
6 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-1-0)       715    222    219      3
6 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   >=0         2010    860    857      3
6 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   <-3         2010     17     15      2
6 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-3--2)     2010     39     38      1
6 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-2--1)     2010    259    253      6
6 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-1-0)      2010    835    830      5
6 months    ki1101329-Keneba           GAMBIA                         >=0         1724    351    346      5
6 months    ki1101329-Keneba           GAMBIA                         <-3         1724     24     20      4
6 months    ki1101329-Keneba           GAMBIA                         [-3--2)     1724    104     87     17
6 months    ki1101329-Keneba           GAMBIA                         [-2--1)     1724    477    457     20
6 months    ki1101329-Keneba           GAMBIA                         [-1-0)      1724    768    758     10
6 months    ki1114097-CMIN             BRAZIL                         >=0          104     50     50      0
6 months    ki1114097-CMIN             BRAZIL                         <-3          104      0      0      0
6 months    ki1114097-CMIN             BRAZIL                         [-3--2)      104      1      1      0
6 months    ki1114097-CMIN             BRAZIL                         [-2--1)      104     16     15      1
6 months    ki1114097-CMIN             BRAZIL                         [-1-0)       104     37     35      2
6 months    ki1114097-CMIN             PERU                           >=0            9      8      8      0
6 months    ki1114097-CMIN             PERU                           <-3            9      0      0      0
6 months    ki1114097-CMIN             PERU                           [-3--2)        9      0      0      0
6 months    ki1114097-CMIN             PERU                           [-2--1)        9      0      0      0
6 months    ki1114097-CMIN             PERU                           [-1-0)         9      1      1      0
6 months    ki1114097-CONTENT          PERU                           >=0            2      1      1      0
6 months    ki1114097-CONTENT          PERU                           <-3            2      0      0      0
6 months    ki1114097-CONTENT          PERU                           [-3--2)        2      0      0      0
6 months    ki1114097-CONTENT          PERU                           [-2--1)        2      0      0      0
6 months    ki1114097-CONTENT          PERU                           [-1-0)         2      1      1      0
6 months    ki1126311-ZVITAMBO         ZIMBABWE                       >=0         8265   1955   1931     24
6 months    ki1126311-ZVITAMBO         ZIMBABWE                       <-3         8265    212    152     60
6 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-3--2)     8265    637    552     85
6 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-2--1)     8265   1949   1848    101
6 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-1-0)      8265   3512   3438     74
6 months    ki1135781-COHORTS          GUATEMALA                      >=0          375    102     94      8
6 months    ki1135781-COHORTS          GUATEMALA                      <-3          375      6      3      3
6 months    ki1135781-COHORTS          GUATEMALA                      [-3--2)      375     36     22     14
6 months    ki1135781-COHORTS          GUATEMALA                      [-2--1)      375    117    104     13
6 months    ki1135781-COHORTS          GUATEMALA                      [-1-0)       375    114    100     14
6 months    ki1135781-COHORTS          INDIA                          >=0         6261    729    724      5
6 months    ki1135781-COHORTS          INDIA                          <-3         6261    231    154     77
6 months    ki1135781-COHORTS          INDIA                          [-3--2)     6261    810    733     77
6 months    ki1135781-COHORTS          INDIA                          [-2--1)     6261   2131   2046     85
6 months    ki1135781-COHORTS          INDIA                          [-1-0)      6261   2360   2331     29
6 months    ki1135781-COHORTS          PHILIPPINES                    >=0         2664    580    573      7
6 months    ki1135781-COHORTS          PHILIPPINES                    <-3         2664     52     35     17
6 months    ki1135781-COHORTS          PHILIPPINES                    [-3--2)     2664    152    132     20
6 months    ki1135781-COHORTS          PHILIPPINES                    [-2--1)     2664    643    597     46
6 months    ki1135781-COHORTS          PHILIPPINES                    [-1-0)      2664   1237   1197     40
9 months    ki0047075b-MAL-ED          BANGLADESH                     >=0          228     33     32      1
9 months    ki0047075b-MAL-ED          BANGLADESH                     <-3          228      4      4      0
9 months    ki0047075b-MAL-ED          BANGLADESH                     [-3--2)      228     34     29      5
9 months    ki0047075b-MAL-ED          BANGLADESH                     [-2--1)      228     81     78      3
9 months    ki0047075b-MAL-ED          BANGLADESH                     [-1-0)       228     76     74      2
9 months    ki0047075b-MAL-ED          BRAZIL                         >=0          199    111    111      0
9 months    ki0047075b-MAL-ED          BRAZIL                         <-3          199      0      0      0
9 months    ki0047075b-MAL-ED          BRAZIL                         [-3--2)      199      8      8      0
9 months    ki0047075b-MAL-ED          BRAZIL                         [-2--1)      199     21     21      0
9 months    ki0047075b-MAL-ED          BRAZIL                         [-1-0)       199     59     59      0
9 months    ki0047075b-MAL-ED          INDIA                          >=0          227     41     41      0
9 months    ki0047075b-MAL-ED          INDIA                          <-3          227      5      2      3
9 months    ki0047075b-MAL-ED          INDIA                          [-3--2)      227     22     19      3
9 months    ki0047075b-MAL-ED          INDIA                          [-2--1)      227     71     68      3
9 months    ki0047075b-MAL-ED          INDIA                          [-1-0)       227     88     87      1
9 months    ki0047075b-MAL-ED          NEPAL                          >=0          224     46     46      0
9 months    ki0047075b-MAL-ED          NEPAL                          <-3          224      3      3      0
9 months    ki0047075b-MAL-ED          NEPAL                          [-3--2)      224     15     15      0
9 months    ki0047075b-MAL-ED          NEPAL                          [-2--1)      224     52     52      0
9 months    ki0047075b-MAL-ED          NEPAL                          [-1-0)       224    108    107      1
9 months    ki0047075b-MAL-ED          PERU                           >=0          253     73     73      0
9 months    ki0047075b-MAL-ED          PERU                           <-3          253      4      4      0
9 months    ki0047075b-MAL-ED          PERU                           [-3--2)      253      9      5      4
9 months    ki0047075b-MAL-ED          PERU                           [-2--1)      253     40     34      6
9 months    ki0047075b-MAL-ED          PERU                           [-1-0)       253    127    125      2
9 months    ki0047075b-MAL-ED          SOUTH AFRICA                   >=0          250     98     97      1
9 months    ki0047075b-MAL-ED          SOUTH AFRICA                   <-3          250      3      3      0
9 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-3--2)      250     10      7      3
9 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-2--1)      250     36     33      3
9 months    ki0047075b-MAL-ED          SOUTH AFRICA                   [-1-0)       250    103    101      2
9 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   >=0          120     54     52      2
9 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   <-3          120      0      0      0
9 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-3--2)      120      4      2      2
9 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-2--1)      120     17     14      3
9 months    ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-1-0)       120     45     40      5
9 months    ki1000108-CMC-V-BCS-2002   INDIA                          >=0          358     67     62      5
9 months    ki1000108-CMC-V-BCS-2002   INDIA                          <-3          358     12      7      5
9 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-3--2)      358     30     21      9
9 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-2--1)      358    104     88     16
9 months    ki1000108-CMC-V-BCS-2002   INDIA                          [-1-0)       358    145    134     11
9 months    ki1000108-IRC              INDIA                          >=0          401     61     59      2
9 months    ki1000108-IRC              INDIA                          <-3          401     11      9      2
9 months    ki1000108-IRC              INDIA                          [-3--2)      401     41     35      6
9 months    ki1000108-IRC              INDIA                          [-2--1)      401    132    116     16
9 months    ki1000108-IRC              INDIA                          [-1-0)       401    156    150      6
9 months    ki1000109-EE               PAKISTAN                       >=0          363     34     30      4
9 months    ki1000109-EE               PAKISTAN                       <-3          363     47     30     17
9 months    ki1000109-EE               PAKISTAN                       [-3--2)      363     67     37     30
9 months    ki1000109-EE               PAKISTAN                       [-2--1)      363    114     85     29
9 months    ki1000109-EE               PAKISTAN                       [-1-0)       363    101     88     13
9 months    ki1000109-ResPak           PAKISTAN                       >=0            6      3      2      1
9 months    ki1000109-ResPak           PAKISTAN                       <-3            6      1      1      0
9 months    ki1000109-ResPak           PAKISTAN                       [-3--2)        6      0      0      0
9 months    ki1000109-ResPak           PAKISTAN                       [-2--1)        6      1      1      0
9 months    ki1000109-ResPak           PAKISTAN                       [-1-0)         6      1      1      0
9 months    ki1017093-NIH-Birth        BANGLADESH                     >=0           17      1      1      0
9 months    ki1017093-NIH-Birth        BANGLADESH                     <-3           17      0      0      0
9 months    ki1017093-NIH-Birth        BANGLADESH                     [-3--2)       17      3      2      1
9 months    ki1017093-NIH-Birth        BANGLADESH                     [-2--1)       17      9      8      1
9 months    ki1017093-NIH-Birth        BANGLADESH                     [-1-0)        17      4      4      0
9 months    ki1017093b-PROVIDE         BANGLADESH                     >=0          605     53     53      0
9 months    ki1017093b-PROVIDE         BANGLADESH                     <-3          605      4      3      1
9 months    ki1017093b-PROVIDE         BANGLADESH                     [-3--2)      605     99     87     12
9 months    ki1017093b-PROVIDE         BANGLADESH                     [-2--1)      605    254    245      9
9 months    ki1017093b-PROVIDE         BANGLADESH                     [-1-0)       605    195    192      3
9 months    ki1017093c-NIH-Crypto      BANGLADESH                     >=0          706     95     95      0
9 months    ki1017093c-NIH-Crypto      BANGLADESH                     <-3          706     22     16      6
9 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-3--2)      706    100     90     10
9 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-2--1)      706    268    259      9
9 months    ki1017093c-NIH-Crypto      BANGLADESH                     [-1-0)       706    221    218      3
9 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   >=0         1771    782    776      6
9 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   <-3         1771     15     15      0
9 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-3--2)     1771     30     28      2
9 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-2--1)     1771    220    208     12
9 months    ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-1-0)      1771    724    710     14
9 months    ki1101329-Keneba           GAMBIA                         >=0         1717    345    340      5
9 months    ki1101329-Keneba           GAMBIA                         <-3         1717     25     16      9
9 months    ki1101329-Keneba           GAMBIA                         [-3--2)     1717    105     84     21
9 months    ki1101329-Keneba           GAMBIA                         [-2--1)     1717    473    441     32
9 months    ki1101329-Keneba           GAMBIA                         [-1-0)      1717    769    750     19
9 months    ki1114097-CMIN             BRAZIL                         >=0          106     52     50      2
9 months    ki1114097-CMIN             BRAZIL                         <-3          106      1      1      0
9 months    ki1114097-CMIN             BRAZIL                         [-3--2)      106      2      2      0
9 months    ki1114097-CMIN             BRAZIL                         [-2--1)      106     16     13      3
9 months    ki1114097-CMIN             BRAZIL                         [-1-0)       106     35     32      3
9 months    ki1114097-CMIN             PERU                           >=0            8      7      7      0
9 months    ki1114097-CMIN             PERU                           <-3            8      0      0      0
9 months    ki1114097-CMIN             PERU                           [-3--2)        8      0      0      0
9 months    ki1114097-CMIN             PERU                           [-2--1)        8      0      0      0
9 months    ki1114097-CMIN             PERU                           [-1-0)         8      1      1      0
9 months    ki1114097-CONTENT          PERU                           >=0            2      1      1      0
9 months    ki1114097-CONTENT          PERU                           <-3            2      0      0      0
9 months    ki1114097-CONTENT          PERU                           [-3--2)        2      0      0      0
9 months    ki1114097-CONTENT          PERU                           [-2--1)        2      0      0      0
9 months    ki1114097-CONTENT          PERU                           [-1-0)         2      1      1      0
9 months    ki1126311-ZVITAMBO         ZIMBABWE                       >=0         7650   1654   1626     28
9 months    ki1126311-ZVITAMBO         ZIMBABWE                       <-3         7650    200    164     36
9 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-3--2)     7650    611    547     64
9 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-2--1)     7650   1893   1755    138
9 months    ki1126311-ZVITAMBO         ZIMBABWE                       [-1-0)      7650   3292   3191    101
9 months    ki1135781-COHORTS          GUATEMALA                      >=0          359     91     80     11
9 months    ki1135781-COHORTS          GUATEMALA                      <-3          359      5      2      3
9 months    ki1135781-COHORTS          GUATEMALA                      [-3--2)      359     39     19     20
9 months    ki1135781-COHORTS          GUATEMALA                      [-2--1)      359    111     81     30
9 months    ki1135781-COHORTS          GUATEMALA                      [-1-0)       359    113     89     24
9 months    ki1135781-COHORTS          INDIA                          >=0         5394    644    640      4
9 months    ki1135781-COHORTS          INDIA                          <-3         5394    202    132     70
9 months    ki1135781-COHORTS          INDIA                          [-3--2)     5394    683    586     97
9 months    ki1135781-COHORTS          INDIA                          [-2--1)     5394   1832   1670    162
9 months    ki1135781-COHORTS          INDIA                          [-1-0)      5394   2033   1971     62
9 months    ki1135781-COHORTS          PHILIPPINES                    >=0         2668    582    567     15
9 months    ki1135781-COHORTS          PHILIPPINES                    <-3         2668     52     34     18
9 months    ki1135781-COHORTS          PHILIPPINES                    [-3--2)     2668    148    117     31
9 months    ki1135781-COHORTS          PHILIPPINES                    [-2--1)     2668    647    578     69
9 months    ki1135781-COHORTS          PHILIPPINES                    [-1-0)      2668   1239   1180     59
12 months   ki0047075b-MAL-ED          BANGLADESH                     >=0          227     33     32      1
12 months   ki0047075b-MAL-ED          BANGLADESH                     <-3          227      4      4      0
12 months   ki0047075b-MAL-ED          BANGLADESH                     [-3--2)      227     34     27      7
12 months   ki0047075b-MAL-ED          BANGLADESH                     [-2--1)      227     81     77      4
12 months   ki0047075b-MAL-ED          BANGLADESH                     [-1-0)       227     75     70      5
12 months   ki0047075b-MAL-ED          BRAZIL                         >=0          195    109    109      0
12 months   ki0047075b-MAL-ED          BRAZIL                         <-3          195      0      0      0
12 months   ki0047075b-MAL-ED          BRAZIL                         [-3--2)      195      8      8      0
12 months   ki0047075b-MAL-ED          BRAZIL                         [-2--1)      195     21     21      0
12 months   ki0047075b-MAL-ED          BRAZIL                         [-1-0)       195     57     57      0
12 months   ki0047075b-MAL-ED          INDIA                          >=0          223     39     37      2
12 months   ki0047075b-MAL-ED          INDIA                          <-3          223      5      3      2
12 months   ki0047075b-MAL-ED          INDIA                          [-3--2)      223     21     18      3
12 months   ki0047075b-MAL-ED          INDIA                          [-2--1)      223     70     64      6
12 months   ki0047075b-MAL-ED          INDIA                          [-1-0)       223     88     83      5
12 months   ki0047075b-MAL-ED          NEPAL                          >=0          224     46     45      1
12 months   ki0047075b-MAL-ED          NEPAL                          <-3          224      3      3      0
12 months   ki0047075b-MAL-ED          NEPAL                          [-3--2)      224     15     14      1
12 months   ki0047075b-MAL-ED          NEPAL                          [-2--1)      224     52     51      1
12 months   ki0047075b-MAL-ED          NEPAL                          [-1-0)       224    108    107      1
12 months   ki0047075b-MAL-ED          PERU                           >=0          243     72     72      0
12 months   ki0047075b-MAL-ED          PERU                           <-3          243      4      3      1
12 months   ki0047075b-MAL-ED          PERU                           [-3--2)      243      8      3      5
12 months   ki0047075b-MAL-ED          PERU                           [-2--1)      243     38     33      5
12 months   ki0047075b-MAL-ED          PERU                           [-1-0)       243    121    119      2
12 months   ki0047075b-MAL-ED          SOUTH AFRICA                   >=0          252     96     95      1
12 months   ki0047075b-MAL-ED          SOUTH AFRICA                   <-3          252      3      3      0
12 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-3--2)      252     10      7      3
12 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-2--1)      252     37     35      2
12 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-1-0)       252    106    100      6
12 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   >=0          117     54     51      3
12 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   <-3          117      0      0      0
12 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-3--2)      117      4      2      2
12 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-2--1)      117     17     14      3
12 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-1-0)       117     42     37      5
12 months   ki1000108-CMC-V-BCS-2002   INDIA                          >=0          360     67     61      6
12 months   ki1000108-CMC-V-BCS-2002   INDIA                          <-3          360     12      6      6
12 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-3--2)      360     30     17     13
12 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-2--1)      360    104     78     26
12 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-1-0)       360    147    118     29
12 months   ki1000108-IRC              INDIA                          >=0          400     61     59      2
12 months   ki1000108-IRC              INDIA                          <-3          400     11      8      3
12 months   ki1000108-IRC              INDIA                          [-3--2)      400     41     35      6
12 months   ki1000108-IRC              INDIA                          [-2--1)      400    131    115     16
12 months   ki1000108-IRC              INDIA                          [-1-0)       400    156    151      5
12 months   ki1000109-EE               PAKISTAN                       >=0          354     32     29      3
12 months   ki1000109-EE               PAKISTAN                       <-3          354     45     24     21
12 months   ki1000109-EE               PAKISTAN                       [-3--2)      354     65     30     35
12 months   ki1000109-EE               PAKISTAN                       [-2--1)      354    113     75     38
12 months   ki1000109-EE               PAKISTAN                       [-1-0)       354     99     78     21
12 months   ki1000109-ResPak           PAKISTAN                       >=0            5      2      2      0
12 months   ki1000109-ResPak           PAKISTAN                       <-3            5      1      1      0
12 months   ki1000109-ResPak           PAKISTAN                       [-3--2)        5      0      0      0
12 months   ki1000109-ResPak           PAKISTAN                       [-2--1)        5      1      1      0
12 months   ki1000109-ResPak           PAKISTAN                       [-1-0)         5      1      1      0
12 months   ki1017093-NIH-Birth        BANGLADESH                     >=0           17      1      1      0
12 months   ki1017093-NIH-Birth        BANGLADESH                     <-3           17      0      0      0
12 months   ki1017093-NIH-Birth        BANGLADESH                     [-3--2)       17      3      1      2
12 months   ki1017093-NIH-Birth        BANGLADESH                     [-2--1)       17      9      8      1
12 months   ki1017093-NIH-Birth        BANGLADESH                     [-1-0)        17      4      4      0
12 months   ki1017093b-PROVIDE         BANGLADESH                     >=0          600     53     52      1
12 months   ki1017093b-PROVIDE         BANGLADESH                     <-3          600      4      4      0
12 months   ki1017093b-PROVIDE         BANGLADESH                     [-3--2)      600     97     83     14
12 months   ki1017093b-PROVIDE         BANGLADESH                     [-2--1)      600    249    232     17
12 months   ki1017093b-PROVIDE         BANGLADESH                     [-1-0)       600    197    193      4
12 months   ki1017093c-NIH-Crypto      BANGLADESH                     >=0          706     90     90      0
12 months   ki1017093c-NIH-Crypto      BANGLADESH                     <-3          706     23     15      8
12 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-3--2)      706    104     88     16
12 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-2--1)      706    268    254     14
12 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-1-0)       706    221    218      3
12 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   >=0         1429    618    614      4
12 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   <-3         1429     12     10      2
12 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-3--2)     1429     25     23      2
12 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-2--1)     1429    178    169      9
12 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-1-0)      1429    596    581     15
12 months   ki1101329-Keneba           GAMBIA                         >=0         1616    333    324      9
12 months   ki1101329-Keneba           GAMBIA                         <-3         1616     22     16      6
12 months   ki1101329-Keneba           GAMBIA                         [-3--2)     1616     95     68     27
12 months   ki1101329-Keneba           GAMBIA                         [-2--1)     1616    443    398     45
12 months   ki1101329-Keneba           GAMBIA                         [-1-0)      1616    723    699     24
12 months   ki1114097-CMIN             BRAZIL                         >=0          111     54     52      2
12 months   ki1114097-CMIN             BRAZIL                         <-3          111      1      1      0
12 months   ki1114097-CMIN             BRAZIL                         [-3--2)      111      2      2      0
12 months   ki1114097-CMIN             BRAZIL                         [-2--1)      111     18     16      2
12 months   ki1114097-CMIN             BRAZIL                         [-1-0)       111     36     32      4
12 months   ki1114097-CMIN             PERU                           >=0            8      7      7      0
12 months   ki1114097-CMIN             PERU                           <-3            8      0      0      0
12 months   ki1114097-CMIN             PERU                           [-3--2)        8      0      0      0
12 months   ki1114097-CMIN             PERU                           [-2--1)        8      0      0      0
12 months   ki1114097-CMIN             PERU                           [-1-0)         8      1      1      0
12 months   ki1114097-CONTENT          PERU                           >=0            2      1      1      0
12 months   ki1114097-CONTENT          PERU                           <-3            2      0      0      0
12 months   ki1114097-CONTENT          PERU                           [-3--2)        2      0      0      0
12 months   ki1114097-CONTENT          PERU                           [-2--1)        2      0      0      0
12 months   ki1114097-CONTENT          PERU                           [-1-0)         2      1      1      0
12 months   ki1126311-ZVITAMBO         ZIMBABWE                       >=0         6731   1345   1321     24
12 months   ki1126311-ZVITAMBO         ZIMBABWE                       <-3         6731    189    144     45
12 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-3--2)     6731    560    480     80
12 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-2--1)     6731   1758   1592    166
12 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-1-0)      6731   2879   2749    130
12 months   ki1135781-COHORTS          GUATEMALA                      >=0          377     98     81     17
12 months   ki1135781-COHORTS          GUATEMALA                      <-3          377      4      1      3
12 months   ki1135781-COHORTS          GUATEMALA                      [-3--2)      377     39     15     24
12 months   ki1135781-COHORTS          GUATEMALA                      [-2--1)      377    117     72     45
12 months   ki1135781-COHORTS          GUATEMALA                      [-1-0)       377    119     87     32
12 months   ki1135781-COHORTS          INDIA                          >=0         4810    580    575      5
12 months   ki1135781-COHORTS          INDIA                          <-3         4810    168    104     64
12 months   ki1135781-COHORTS          INDIA                          [-3--2)     4810    596    474    122
12 months   ki1135781-COHORTS          INDIA                          [-2--1)     4810   1629   1414    215
12 months   ki1135781-COHORTS          INDIA                          [-1-0)      4810   1837   1725    112
12 months   ki1135781-COHORTS          PHILIPPINES                    >=0         2544    566    537     29
12 months   ki1135781-COHORTS          PHILIPPINES                    <-3         2544     47     29     18
12 months   ki1135781-COHORTS          PHILIPPINES                    [-3--2)     2544    141     97     44
12 months   ki1135781-COHORTS          PHILIPPINES                    [-2--1)     2544    617    490    127
12 months   ki1135781-COHORTS          PHILIPPINES                    [-1-0)      2544   1173   1054    119
18 months   ki0047075b-MAL-ED          BANGLADESH                     >=0          216     32     30      2
18 months   ki0047075b-MAL-ED          BANGLADESH                     <-3          216      4      4      0
18 months   ki0047075b-MAL-ED          BANGLADESH                     [-3--2)      216     32     22     10
18 months   ki0047075b-MAL-ED          BANGLADESH                     [-2--1)      216     77     68      9
18 months   ki0047075b-MAL-ED          BANGLADESH                     [-1-0)       216     71     62      9
18 months   ki0047075b-MAL-ED          BRAZIL                         >=0          180    101    101      0
18 months   ki0047075b-MAL-ED          BRAZIL                         <-3          180      0      0      0
18 months   ki0047075b-MAL-ED          BRAZIL                         [-3--2)      180      7      7      0
18 months   ki0047075b-MAL-ED          BRAZIL                         [-2--1)      180     19     19      0
18 months   ki0047075b-MAL-ED          BRAZIL                         [-1-0)       180     53     53      0
18 months   ki0047075b-MAL-ED          INDIA                          >=0          223     38     35      3
18 months   ki0047075b-MAL-ED          INDIA                          <-3          223      5      2      3
18 months   ki0047075b-MAL-ED          INDIA                          [-3--2)      223     22     15      7
18 months   ki0047075b-MAL-ED          INDIA                          [-2--1)      223     70     59     11
18 months   ki0047075b-MAL-ED          INDIA                          [-1-0)       223     88     81      7
18 months   ki0047075b-MAL-ED          NEPAL                          >=0          222     46     45      1
18 months   ki0047075b-MAL-ED          NEPAL                          <-3          222      3      3      0
18 months   ki0047075b-MAL-ED          NEPAL                          [-3--2)      222     15     13      2
18 months   ki0047075b-MAL-ED          NEPAL                          [-2--1)      222     52     51      1
18 months   ki0047075b-MAL-ED          NEPAL                          [-1-0)       222    106    104      2
18 months   ki0047075b-MAL-ED          PERU                           >=0          219     64     63      1
18 months   ki0047075b-MAL-ED          PERU                           <-3          219      3      3      0
18 months   ki0047075b-MAL-ED          PERU                           [-3--2)      219      7      2      5
18 months   ki0047075b-MAL-ED          PERU                           [-2--1)      219     38     32      6
18 months   ki0047075b-MAL-ED          PERU                           [-1-0)       219    107    100      7
18 months   ki0047075b-MAL-ED          SOUTH AFRICA                   >=0          241     91     84      7
18 months   ki0047075b-MAL-ED          SOUTH AFRICA                   <-3          241      3      3      0
18 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-3--2)      241      9      5      4
18 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-2--1)      241     34     30      4
18 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-1-0)       241    104     93     11
18 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   >=0          112     51     40     11
18 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   <-3          112      0      0      0
18 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-3--2)      112      4      0      4
18 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-2--1)      112     17     12      5
18 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-1-0)       112     40     31      9
18 months   ki1000108-CMC-V-BCS-2002   INDIA                          >=0          361     68     56     12
18 months   ki1000108-CMC-V-BCS-2002   INDIA                          <-3          361     12      5      7
18 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-3--2)      361     30     12     18
18 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-2--1)      361    105     67     38
18 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-1-0)       361    146    115     31
18 months   ki1000108-IRC              INDIA                          >=0          399     61     60      1
18 months   ki1000108-IRC              INDIA                          <-3          399     11      9      2
18 months   ki1000108-IRC              INDIA                          [-3--2)      399     40     33      7
18 months   ki1000108-IRC              INDIA                          [-2--1)      399    131    113     18
18 months   ki1000108-IRC              INDIA                          [-1-0)       399    156    153      3
18 months   ki1000109-EE               PAKISTAN                       >=0          347     33     26      7
18 months   ki1000109-EE               PAKISTAN                       <-3          347     45     16     29
18 months   ki1000109-EE               PAKISTAN                       [-3--2)      347     63     21     42
18 months   ki1000109-EE               PAKISTAN                       [-2--1)      347    111     54     57
18 months   ki1000109-EE               PAKISTAN                       [-1-0)       347     95     61     34
18 months   ki1000109-ResPak           PAKISTAN                       >=0            1      0      0      0
18 months   ki1000109-ResPak           PAKISTAN                       <-3            1      0      0      0
18 months   ki1000109-ResPak           PAKISTAN                       [-3--2)        1      0      0      0
18 months   ki1000109-ResPak           PAKISTAN                       [-2--1)        1      1      1      0
18 months   ki1000109-ResPak           PAKISTAN                       [-1-0)         1      0      0      0
18 months   ki1017093-NIH-Birth        BANGLADESH                     >=0           17      1      1      0
18 months   ki1017093-NIH-Birth        BANGLADESH                     <-3           17      0      0      0
18 months   ki1017093-NIH-Birth        BANGLADESH                     [-3--2)       17      3      1      2
18 months   ki1017093-NIH-Birth        BANGLADESH                     [-2--1)       17      9      9      0
18 months   ki1017093-NIH-Birth        BANGLADESH                     [-1-0)        17      4      3      1
18 months   ki1017093b-PROVIDE         BANGLADESH                     >=0          552     50     50      0
18 months   ki1017093b-PROVIDE         BANGLADESH                     <-3          552      4      3      1
18 months   ki1017093b-PROVIDE         BANGLADESH                     [-3--2)      552     87     68     19
18 months   ki1017093b-PROVIDE         BANGLADESH                     [-2--1)      552    231    201     30
18 months   ki1017093b-PROVIDE         BANGLADESH                     [-1-0)       552    180    173      7
18 months   ki1017093c-NIH-Crypto      BANGLADESH                     >=0          634     74     74      0
18 months   ki1017093c-NIH-Crypto      BANGLADESH                     <-3          634     23     15      8
18 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-3--2)      634     98     81     17
18 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-2--1)      634    243    231     12
18 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-1-0)       634    196    191      5
18 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   >=0          969    425    420      5
18 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   <-3          969      5      4      1
18 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-3--2)      969     14     12      2
18 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-2--1)      969    124    114     10
18 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-1-0)       969    401    380     21
18 months   ki1101329-Keneba           GAMBIA                         >=0         1618    319    310      9
18 months   ki1101329-Keneba           GAMBIA                         <-3         1618     22     15      7
18 months   ki1101329-Keneba           GAMBIA                         [-3--2)     1618     98     69     29
18 months   ki1101329-Keneba           GAMBIA                         [-2--1)     1618    436    375     61
18 months   ki1101329-Keneba           GAMBIA                         [-1-0)      1618    743    699     44
18 months   ki1114097-CMIN             BRAZIL                         >=0          111     54     52      2
18 months   ki1114097-CMIN             BRAZIL                         <-3          111      1      1      0
18 months   ki1114097-CMIN             BRAZIL                         [-3--2)      111      2      2      0
18 months   ki1114097-CMIN             BRAZIL                         [-2--1)      111     16     15      1
18 months   ki1114097-CMIN             BRAZIL                         [-1-0)       111     38     33      5
18 months   ki1114097-CMIN             PERU                           >=0            8      7      7      0
18 months   ki1114097-CMIN             PERU                           <-3            8      0      0      0
18 months   ki1114097-CMIN             PERU                           [-3--2)        8      0      0      0
18 months   ki1114097-CMIN             PERU                           [-2--1)        8      0      0      0
18 months   ki1114097-CMIN             PERU                           [-1-0)         8      1      1      0
18 months   ki1114097-CONTENT          PERU                           >=0            2      1      1      0
18 months   ki1114097-CONTENT          PERU                           <-3            2      0      0      0
18 months   ki1114097-CONTENT          PERU                           [-3--2)        2      0      0      0
18 months   ki1114097-CONTENT          PERU                           [-2--1)        2      0      0      0
18 months   ki1114097-CONTENT          PERU                           [-1-0)         2      1      1      0
18 months   ki1126311-ZVITAMBO         ZIMBABWE                       >=0         1707    250    228     22
18 months   ki1126311-ZVITAMBO         ZIMBABWE                       <-3         1707     60     43     17
18 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-3--2)     1707    177    126     51
18 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-2--1)     1707    501    384    117
18 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-1-0)      1707    719    628     91
18 months   ki1135781-COHORTS          GUATEMALA                      >=0          302     73     48     25
18 months   ki1135781-COHORTS          GUATEMALA                      <-3          302      5      1      4
18 months   ki1135781-COHORTS          GUATEMALA                      [-3--2)      302     33      9     24
18 months   ki1135781-COHORTS          GUATEMALA                      [-2--1)      302     95     43     52
18 months   ki1135781-COHORTS          GUATEMALA                      [-1-0)       302     96     50     46
18 months   ki1135781-COHORTS          PHILIPPINES                    >=0         2451    542    457     85
18 months   ki1135781-COHORTS          PHILIPPINES                    <-3         2451     39     21     18
18 months   ki1135781-COHORTS          PHILIPPINES                    [-3--2)     2451    138     71     67
18 months   ki1135781-COHORTS          PHILIPPINES                    [-2--1)     2451    579    393    186
18 months   ki1135781-COHORTS          PHILIPPINES                    [-1-0)      2451   1153    894    259
24 months   ki0047075b-MAL-ED          BANGLADESH                     >=0          207     31     29      2
24 months   ki0047075b-MAL-ED          BANGLADESH                     <-3          207      4      3      1
24 months   ki0047075b-MAL-ED          BANGLADESH                     [-3--2)      207     29     22      7
24 months   ki0047075b-MAL-ED          BANGLADESH                     [-2--1)      207     73     65      8
24 months   ki0047075b-MAL-ED          BANGLADESH                     [-1-0)       207     70     63      7
24 months   ki0047075b-MAL-ED          BRAZIL                         >=0          169     96     96      0
24 months   ki0047075b-MAL-ED          BRAZIL                         <-3          169      0      0      0
24 months   ki0047075b-MAL-ED          BRAZIL                         [-3--2)      169      7      7      0
24 months   ki0047075b-MAL-ED          BRAZIL                         [-2--1)      169     17     17      0
24 months   ki0047075b-MAL-ED          BRAZIL                         [-1-0)       169     49     48      1
24 months   ki0047075b-MAL-ED          INDIA                          >=0          222     38     36      2
24 months   ki0047075b-MAL-ED          INDIA                          <-3          222      5      2      3
24 months   ki0047075b-MAL-ED          INDIA                          [-3--2)      222     22     17      5
24 months   ki0047075b-MAL-ED          INDIA                          [-2--1)      222     69     59     10
24 months   ki0047075b-MAL-ED          INDIA                          [-1-0)       222     88     80      8
24 months   ki0047075b-MAL-ED          NEPAL                          >=0          221     45     44      1
24 months   ki0047075b-MAL-ED          NEPAL                          <-3          221      3      3      0
24 months   ki0047075b-MAL-ED          NEPAL                          [-3--2)      221     15     14      1
24 months   ki0047075b-MAL-ED          NEPAL                          [-2--1)      221     52     50      2
24 months   ki0047075b-MAL-ED          NEPAL                          [-1-0)       221    106    104      2
24 months   ki0047075b-MAL-ED          PERU                           >=0          198     57     56      1
24 months   ki0047075b-MAL-ED          PERU                           <-3          198      3      2      1
24 months   ki0047075b-MAL-ED          PERU                           [-3--2)      198      6      0      6
24 months   ki0047075b-MAL-ED          PERU                           [-2--1)      198     35     31      4
24 months   ki0047075b-MAL-ED          PERU                           [-1-0)       198     97     95      2
24 months   ki0047075b-MAL-ED          SOUTH AFRICA                   >=0          238     89     82      7
24 months   ki0047075b-MAL-ED          SOUTH AFRICA                   <-3          238      3      3      0
24 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-3--2)      238      8      5      3
24 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-2--1)      238     34     30      4
24 months   ki0047075b-MAL-ED          SOUTH AFRICA                   [-1-0)       238    104     92     12
24 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   >=0          106     49     40      9
24 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   <-3          106      0      0      0
24 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-3--2)      106      4      0      4
24 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-2--1)      106     15     10      5
24 months   ki0047075b-MAL-ED          TANZANIA, UNITED REPUBLIC OF   [-1-0)       106     38     25     13
24 months   ki1000108-CMC-V-BCS-2002   INDIA                          >=0          364     69     59     10
24 months   ki1000108-CMC-V-BCS-2002   INDIA                          <-3          364     12      5      7
24 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-3--2)      364     30     11     19
24 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-2--1)      364    106     62     44
24 months   ki1000108-CMC-V-BCS-2002   INDIA                          [-1-0)       364    147    108     39
24 months   ki1000108-IRC              INDIA                          >=0          403     61     61      0
24 months   ki1000108-IRC              INDIA                          <-3          403     12      9      3
24 months   ki1000108-IRC              INDIA                          [-3--2)      403     41     29     12
24 months   ki1000108-IRC              INDIA                          [-2--1)      403    133    117     16
24 months   ki1000108-IRC              INDIA                          [-1-0)       403    156    150      6
24 months   ki1017093-NIH-Birth        BANGLADESH                     >=0           16      1      1      0
24 months   ki1017093-NIH-Birth        BANGLADESH                     <-3           16      0      0      0
24 months   ki1017093-NIH-Birth        BANGLADESH                     [-3--2)       16      3      1      2
24 months   ki1017093-NIH-Birth        BANGLADESH                     [-2--1)       16      8      7      1
24 months   ki1017093-NIH-Birth        BANGLADESH                     [-1-0)        16      4      4      0
24 months   ki1017093b-PROVIDE         BANGLADESH                     >=0          577     51     51      0
24 months   ki1017093b-PROVIDE         BANGLADESH                     <-3          577      4      3      1
24 months   ki1017093b-PROVIDE         BANGLADESH                     [-3--2)      577     94     78     16
24 months   ki1017093b-PROVIDE         BANGLADESH                     [-2--1)      577    243    217     26
24 months   ki1017093b-PROVIDE         BANGLADESH                     [-1-0)       577    185    179      6
24 months   ki1017093c-NIH-Crypto      BANGLADESH                     >=0          514     60     60      0
24 months   ki1017093c-NIH-Crypto      BANGLADESH                     <-3          514     17      9      8
24 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-3--2)      514     81     68     13
24 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-2--1)      514    197    187     10
24 months   ki1017093c-NIH-Crypto      BANGLADESH                     [-1-0)       514    159    155      4
24 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   >=0            6      3      2      1
24 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   <-3            6      0      0      0
24 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-3--2)        6      0      0      0
24 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-2--1)        6      2      2      0
24 months   ki1066203-TanzaniaChild2   TANZANIA, UNITED REPUBLIC OF   [-1-0)         6      1      1      0
24 months   ki1101329-Keneba           GAMBIA                         >=0         1435    284    274     10
24 months   ki1101329-Keneba           GAMBIA                         <-3         1435     19     13      6
24 months   ki1101329-Keneba           GAMBIA                         [-3--2)     1435     89     64     25
24 months   ki1101329-Keneba           GAMBIA                         [-2--1)     1435    397    349     48
24 months   ki1101329-Keneba           GAMBIA                         [-1-0)      1435    646    615     31
24 months   ki1114097-CMIN             PERU                           >=0            3      2      2      0
24 months   ki1114097-CMIN             PERU                           <-3            3      0      0      0
24 months   ki1114097-CMIN             PERU                           [-3--2)        3      0      0      0
24 months   ki1114097-CMIN             PERU                           [-2--1)        3      0      0      0
24 months   ki1114097-CMIN             PERU                           [-1-0)         3      1      1      0
24 months   ki1114097-CONTENT          PERU                           >=0            2      1      1      0
24 months   ki1114097-CONTENT          PERU                           <-3            2      0      0      0
24 months   ki1114097-CONTENT          PERU                           [-3--2)        2      0      0      0
24 months   ki1114097-CONTENT          PERU                           [-2--1)        2      0      0      0
24 months   ki1114097-CONTENT          PERU                           [-1-0)         2      1      1      0
24 months   ki1126311-ZVITAMBO         ZIMBABWE                       >=0          455     55     46      9
24 months   ki1126311-ZVITAMBO         ZIMBABWE                       <-3          455     15     10      5
24 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-3--2)      455     57     29     28
24 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-2--1)      455    156    110     46
24 months   ki1126311-ZVITAMBO         ZIMBABWE                       [-1-0)       455    172    130     42
24 months   ki1135781-COHORTS          GUATEMALA                      >=0          308     68     45     23
24 months   ki1135781-COHORTS          GUATEMALA                      <-3          308      5      0      5
24 months   ki1135781-COHORTS          GUATEMALA                      [-3--2)      308     35      7     28
24 months   ki1135781-COHORTS          GUATEMALA                      [-2--1)      308    103     46     57
24 months   ki1135781-COHORTS          GUATEMALA                      [-1-0)       308     97     52     45
24 months   ki1135781-COHORTS          INDIA                          >=0         4861    609    579     30
24 months   ki1135781-COHORTS          INDIA                          <-3         4861    161     72     89
24 months   ki1135781-COHORTS          INDIA                          [-3--2)     4861    598    415    183
24 months   ki1135781-COHORTS          INDIA                          [-2--1)     4861   1646   1280    366
24 months   ki1135781-COHORTS          INDIA                          [-1-0)      4861   1847   1640    207
24 months   ki1135781-COHORTS          PHILIPPINES                    >=0         2404    519    419    100
24 months   ki1135781-COHORTS          PHILIPPINES                    <-3         2404     39     19     20
24 months   ki1135781-COHORTS          PHILIPPINES                    [-3--2)     2404    132     68     64
24 months   ki1135781-COHORTS          PHILIPPINES                    [-2--1)     2404    578    383    195
24 months   ki1135781-COHORTS          PHILIPPINES                    [-1-0)      2404   1136    841    295


The following strata were considered:

* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 12 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 12 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 12 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 12 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 12 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 12 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 12 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 12 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 12 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 12 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 12 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 12 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 12 months, studyid: ki1126311-ZVITAMBO, country: ZIMBABWE
* agecat: 12 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 12 months, studyid: ki1135781-COHORTS, country: INDIA
* agecat: 12 months, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 18 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 18 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 18 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 18 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 18 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 18 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 18 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 18 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 18 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 18 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 18 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 18 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 18 months, studyid: ki1126311-ZVITAMBO, country: ZIMBABWE
* agecat: 18 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 18 months, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 24 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 24 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 24 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 24 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 24 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 24 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 24 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 24 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 24 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 24 months, studyid: ki1126311-ZVITAMBO, country: ZIMBABWE
* agecat: 24 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 24 months, studyid: ki1135781-COHORTS, country: INDIA
* agecat: 24 months, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 3 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 3 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 3 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 3 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 3 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 3 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 3 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 3 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 3 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 3 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 3 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 3 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 3 months, studyid: ki1126311-ZVITAMBO, country: ZIMBABWE
* agecat: 3 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 3 months, studyid: ki1135781-COHORTS, country: INDIA
* agecat: 3 months, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 6 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 6 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 6 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 6 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 6 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 6 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 6 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 6 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 6 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 6 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 6 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 6 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 6 months, studyid: ki1126311-ZVITAMBO, country: ZIMBABWE
* agecat: 6 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 6 months, studyid: ki1135781-COHORTS, country: INDIA
* agecat: 6 months, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 9 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 9 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 9 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 9 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 9 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 9 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 9 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 9 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 9 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 9 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 9 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 9 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 9 months, studyid: ki1126311-ZVITAMBO, country: ZIMBABWE
* agecat: 9 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 9 months, studyid: ki1135781-COHORTS, country: INDIA
* agecat: 9 months, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: Birth, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: Birth, studyid: ki1000108-IRC, country: INDIA
* agecat: Birth, studyid: ki1000109-EE, country: PAKISTAN
* agecat: Birth, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: Birth, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: Birth, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: Birth, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: Birth, studyid: ki1114097-CMIN, country: BANGLADESH
* agecat: Birth, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: Birth, studyid: ki1114097-CMIN, country: PERU
* agecat: Birth, studyid: ki1114097-CONTENT, country: PERU
* agecat: Birth, studyid: ki1126311-ZVITAMBO, country: ZIMBABWE
* agecat: Birth, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: Birth, studyid: ki1135781-COHORTS, country: INDIA
* agecat: Birth, studyid: ki1135781-COHORTS, country: PHILIPPINES

### Dropped Strata

Some strata were dropped due to rare outcomes:

* agecat: Birth, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: Birth, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: Birth, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: Birth, studyid: ki1000108-IRC, country: INDIA
* agecat: Birth, studyid: ki1000109-EE, country: PAKISTAN
* agecat: Birth, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: Birth, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: Birth, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: Birth, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: Birth, studyid: ki1114097-CMIN, country: BANGLADESH
* agecat: Birth, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: Birth, studyid: ki1114097-CMIN, country: PERU
* agecat: Birth, studyid: ki1114097-CONTENT, country: PERU
* agecat: Birth, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: Birth, studyid: ki1135781-COHORTS, country: INDIA
* agecat: Birth, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 3 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 3 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 3 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 3 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 3 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 3 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 3 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 3 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 3 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 3 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 3 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 3 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 3 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 3 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 3 months, studyid: ki1135781-COHORTS, country: INDIA
* agecat: 3 months, studyid: ki1135781-COHORTS, country: PHILIPPINES
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 6 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 6 months, studyid: ki1000108-CMC-V-BCS-2002, country: INDIA
* agecat: 6 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 6 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 6 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 6 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 6 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 6 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 6 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 6 months, studyid: ki1101329-Keneba, country: GAMBIA
* agecat: 6 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 6 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 6 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 6 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 9 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 9 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 9 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 9 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 9 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 9 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 9 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 9 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 9 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 9 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 9 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 9 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 9 months, studyid: ki1135781-COHORTS, country: INDIA
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 12 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 12 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 12 months, studyid: ki1000109-EE, country: PAKISTAN
* agecat: 12 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 12 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 12 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 12 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 12 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 12 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 12 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 12 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 12 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 18 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 18 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 18 months, studyid: ki1000109-ResPak, country: PAKISTAN
* agecat: 18 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 18 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 18 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 18 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 18 months, studyid: ki1114097-CMIN, country: BRAZIL
* agecat: 18 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 18 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 18 months, studyid: ki1135781-COHORTS, country: GUATEMALA
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: BANGLADESH
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: BRAZIL
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: INDIA
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: NEPAL
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: PERU
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: SOUTH AFRICA
* agecat: 24 months, studyid: ki0047075b-MAL-ED, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 24 months, studyid: ki1000108-IRC, country: INDIA
* agecat: 24 months, studyid: ki1017093-NIH-Birth, country: BANGLADESH
* agecat: 24 months, studyid: ki1017093b-PROVIDE, country: BANGLADESH
* agecat: 24 months, studyid: ki1017093c-NIH-Crypto, country: BANGLADESH
* agecat: 24 months, studyid: ki1066203-TanzaniaChild2, country: TANZANIA, UNITED REPUBLIC OF
* agecat: 24 months, studyid: ki1114097-CMIN, country: PERU
* agecat: 24 months, studyid: ki1114097-CONTENT, country: PERU
* agecat: 24 months, studyid: ki1135781-COHORTS, country: GUATEMALA

## Methods Detail

We're interested in the causal parameters $E[Y_a]$ for all values of $a \in \mathcal{A}$. These parameters represent the mean outcome if, possibly contrary to fact, we intervened to set all units to have $A=a$. Under the randomization and positivity assumptions, these are identified by the statistical parameters $\psi_a=E_W[E_{Y|A,W}(Y|A=a,W)]$.  In addition, we're interested in the mean of $Y$, $E[Y]$ under no intervention (the observed mean). We will estimate these parameters by using SuperLearner to fit the relevant likelihood factors -- $E_{Y|A,W}(Y|A=a,W)$ and $p(A=a|W)$, and then updating our likelihood fit using a joint TMLE.

For unadjusted analyses ($W=\{\}$), initial likelihoods were estimated using Lrnr_glm to estimate the simple $E(Y|A)$ and Lrnr_mean to estimate $p(A)$. For adjusted analyses, a small library containing Lrnr_glmnet, Lrnr_xgboost, and Lrnr_mean was used.

Having estimated these parameters, we will then use the delta method to estimate relative risks and attributable risks relative to a prespecified baseline level of $A$.

todo: add detail about dropping strata with rare outcomes, handling missingness







# Results Detail

## Results Plots
![](/tmp/aae39a43-1fe2-4969-826a-55937fca0591/REPORT_files/figure-html/plot_tsm-1.png)<!-- -->


```
## Warning: Removed 24 rows containing missing values (geom_errorbar).
```

![](/tmp/aae39a43-1fe2-4969-826a-55937fca0591/REPORT_files/figure-html/plot_rr-1.png)<!-- -->

![](/tmp/aae39a43-1fe2-4969-826a-55937fca0591/REPORT_files/figure-html/plot_paf-1.png)<!-- -->

![](/tmp/aae39a43-1fe2-4969-826a-55937fca0591/REPORT_files/figure-html/plot_par-1.png)<!-- -->

## Results Table

### Parameter: TSM


agecat      studyid                    country       intervention_level   baseline_level     estimate    ci_lower    ci_upper
----------  -------------------------  ------------  -------------------  ---------------  ----------  ----------  ----------
Birth       ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0028382   0.0009865   0.0046899
Birth       ki1126311-ZVITAMBO         ZIMBABWE      <-3                  NA                0.3465347   0.3001304   0.3929389
Birth       ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              NA                0.1288396   0.1096585   0.1480207
Birth       ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              NA                0.0298954   0.0241240   0.0356667
Birth       ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               NA                0.0071453   0.0049659   0.0093248
3 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0101711   0.0059424   0.0143998
3 months    ki1126311-ZVITAMBO         ZIMBABWE      <-3                  NA                0.5514403   0.4889046   0.6139760
3 months    ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              NA                0.1680556   0.1407419   0.1953692
3 months    ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              NA                0.0629562   0.0527878   0.0731246
3 months    ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               NA                0.0283485   0.0231023   0.0335947
6 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0122762   0.0073947   0.0171577
6 months    ki1126311-ZVITAMBO         ZIMBABWE      <-3                  NA                0.2830189   0.2223776   0.3436601
6 months    ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              NA                0.1334380   0.1070295   0.1598465
6 months    ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              NA                0.0518214   0.0419798   0.0616631
6 months    ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               NA                0.0210706   0.0163204   0.0258208
6 months    ki1135781-COHORTS          INDIA         >=0                  NA                0.0068587   0.0008671   0.0128504
6 months    ki1135781-COHORTS          INDIA         <-3                  NA                0.3333333   0.2725380   0.3941287
6 months    ki1135781-COHORTS          INDIA         [-3--2)              NA                0.0950617   0.0748617   0.1152618
6 months    ki1135781-COHORTS          INDIA         [-2--1)              NA                0.0398874   0.0315780   0.0481968
6 months    ki1135781-COHORTS          INDIA         [-1-0)               NA                0.0122881   0.0078430   0.0167333
6 months    ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0120690   0.0031808   0.0209572
6 months    ki1135781-COHORTS          PHILIPPINES   <-3                  NA                0.3269231   0.1994017   0.4544445
6 months    ki1135781-COHORTS          PHILIPPINES   [-3--2)              NA                0.1315789   0.0778305   0.1853274
6 months    ki1135781-COHORTS          PHILIPPINES   [-2--1)              NA                0.0715397   0.0516155   0.0914638
6 months    ki1135781-COHORTS          PHILIPPINES   [-1-0)               NA                0.0323363   0.0224769   0.0421957
9 months    ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.0746269   0.0116147   0.1376390
9 months    ki1000108-CMC-V-BCS-2002   INDIA         <-3                  NA                0.4166667   0.1373366   0.6959967
9 months    ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              NA                0.3000000   0.1357881   0.4642119
9 months    ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              NA                0.1538462   0.0844066   0.2232857
9 months    ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               NA                0.0758621   0.0327050   0.1190192
9 months    ki1101329-Keneba           GAMBIA        >=0                  NA                0.0144928   0.0018782   0.0271073
9 months    ki1101329-Keneba           GAMBIA        <-3                  NA                0.3600000   0.1717886   0.5482114
9 months    ki1101329-Keneba           GAMBIA        [-3--2)              NA                0.2000000   0.1234686   0.2765314
9 months    ki1101329-Keneba           GAMBIA        [-2--1)              NA                0.0676533   0.0450132   0.0902933
9 months    ki1101329-Keneba           GAMBIA        [-1-0)               NA                0.0247074   0.0137327   0.0356821
9 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0169287   0.0107112   0.0231461
9 months    ki1126311-ZVITAMBO         ZIMBABWE      <-3                  NA                0.1800000   0.1267518   0.2332482
9 months    ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              NA                0.1047463   0.0804635   0.1290291
9 months    ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              NA                0.0729002   0.0611882   0.0846121
9 months    ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               NA                0.0306804   0.0247891   0.0365717
9 months    ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0257732   0.0128972   0.0386492
9 months    ki1135781-COHORTS          PHILIPPINES   <-3                  NA                0.3461538   0.2168236   0.4754841
9 months    ki1135781-COHORTS          PHILIPPINES   [-3--2)              NA                0.2094595   0.1438886   0.2750303
9 months    ki1135781-COHORTS          PHILIPPINES   [-2--1)              NA                0.1066461   0.0828579   0.1304343
9 months    ki1135781-COHORTS          PHILIPPINES   [-1-0)               NA                0.0476190   0.0357589   0.0594792
12 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.0895522   0.0210854   0.1580191
12 months   ki1000108-CMC-V-BCS-2002   INDIA         <-3                  NA                0.5000000   0.2167098   0.7832902
12 months   ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              NA                0.4333333   0.2557647   0.6109020
12 months   ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              NA                0.2500000   0.1666633   0.3333367
12 months   ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               NA                0.1972789   0.1328596   0.2616982
12 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.0270270   0.0096045   0.0444495
12 months   ki1101329-Keneba           GAMBIA        <-3                  NA                0.2727273   0.0865682   0.4588863
12 months   ki1101329-Keneba           GAMBIA        [-3--2)              NA                0.2842105   0.1934842   0.3749369
12 months   ki1101329-Keneba           GAMBIA        [-2--1)              NA                0.1015801   0.0734401   0.1297202
12 months   ki1101329-Keneba           GAMBIA        [-1-0)               NA                0.0331950   0.0201327   0.0462573
12 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0178439   0.0107684   0.0249193
12 months   ki1126311-ZVITAMBO         ZIMBABWE      <-3                  NA                0.2380952   0.1773692   0.2988213
12 months   ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              NA                0.1428571   0.1138728   0.1718415
12 months   ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              NA                0.0944255   0.0807552   0.1080958
12 months   ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               NA                0.0451546   0.0375692   0.0527399
12 months   ki1135781-COHORTS          INDIA         >=0                  NA                0.0086207   0.0010963   0.0161451
12 months   ki1135781-COHORTS          INDIA         <-3                  NA                0.3809524   0.3075118   0.4543929
12 months   ki1135781-COHORTS          INDIA         [-3--2)              NA                0.2046980   0.1723019   0.2370941
12 months   ki1135781-COHORTS          INDIA         [-2--1)              NA                0.1319828   0.1155446   0.1484211
12 months   ki1135781-COHORTS          INDIA         [-1-0)               NA                0.0609690   0.0500261   0.0719119
12 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0512367   0.0330693   0.0694042
12 months   ki1135781-COHORTS          PHILIPPINES   <-3                  NA                0.3829787   0.2439764   0.5219810
12 months   ki1135781-COHORTS          PHILIPPINES   [-3--2)              NA                0.3120567   0.2355646   0.3885489
12 months   ki1135781-COHORTS          PHILIPPINES   [-2--1)              NA                0.2058347   0.1739262   0.2377431
12 months   ki1135781-COHORTS          PHILIPPINES   [-1-0)               NA                0.1014493   0.0841678   0.1187307
18 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.1764706   0.0857362   0.2672049
18 months   ki1000108-CMC-V-BCS-2002   INDIA         <-3                  NA                0.5833333   0.3040065   0.8626601
18 months   ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              NA                0.6000000   0.4244522   0.7755478
18 months   ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              NA                0.3619048   0.2698607   0.4539488
18 months   ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               NA                0.2123288   0.1459008   0.2787567
18 months   ki1000109-EE               PAKISTAN      >=0                  NA                0.2121212   0.0724395   0.3518029
18 months   ki1000109-EE               PAKISTAN      <-3                  NA                0.6444444   0.5043842   0.7845047
18 months   ki1000109-EE               PAKISTAN      [-3--2)              NA                0.6666667   0.5500936   0.7832397
18 months   ki1000109-EE               PAKISTAN      [-2--1)              NA                0.5135135   0.4203974   0.6066296
18 months   ki1000109-EE               PAKISTAN      [-1-0)               NA                0.3578947   0.2613577   0.4544317
18 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.0282132   0.0100372   0.0463892
18 months   ki1101329-Keneba           GAMBIA        <-3                  NA                0.3181818   0.1234921   0.5128715
18 months   ki1101329-Keneba           GAMBIA        [-3--2)              NA                0.2959184   0.2055187   0.3863180
18 months   ki1101329-Keneba           GAMBIA        [-2--1)              NA                0.1399083   0.1073371   0.1724794
18 months   ki1101329-Keneba           GAMBIA        [-1-0)               NA                0.0592194   0.0422423   0.0761965
18 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0880000   0.0528728   0.1231273
18 months   ki1126311-ZVITAMBO         ZIMBABWE      <-3                  NA                0.2833333   0.1692802   0.3973864
18 months   ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              NA                0.2881356   0.2213957   0.3548755
18 months   ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              NA                0.2335329   0.1964753   0.2705905
18 months   ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               NA                0.1265647   0.1022548   0.1508745
18 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.1568266   0.1262066   0.1874466
18 months   ki1135781-COHORTS          PHILIPPINES   <-3                  NA                0.4615385   0.3050488   0.6180281
18 months   ki1135781-COHORTS          PHILIPPINES   [-3--2)              NA                0.4855072   0.4021037   0.5689108
18 months   ki1135781-COHORTS          PHILIPPINES   [-2--1)              NA                0.3212435   0.2832008   0.3592862
18 months   ki1135781-COHORTS          PHILIPPINES   [-1-0)               NA                0.2246314   0.2005373   0.2487255
24 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.1449275   0.0617516   0.2281035
24 months   ki1000108-CMC-V-BCS-2002   INDIA         <-3                  NA                0.5833333   0.3040097   0.8626569
24 months   ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              NA                0.6333333   0.4606554   0.8060112
24 months   ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              NA                0.4150943   0.3211634   0.5090253
24 months   ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               NA                0.2653061   0.1938378   0.3367745
24 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.0352113   0.0137677   0.0566548
24 months   ki1101329-Keneba           GAMBIA        <-3                  NA                0.3157895   0.1067076   0.5248713
24 months   ki1101329-Keneba           GAMBIA        [-3--2)              NA                0.2808989   0.1874929   0.3743048
24 months   ki1101329-Keneba           GAMBIA        [-2--1)              NA                0.1209068   0.0888259   0.1529877
24 months   ki1101329-Keneba           GAMBIA        [-1-0)               NA                0.0479876   0.0314996   0.0644757
24 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.1636364   0.0657591   0.2615137
24 months   ki1126311-ZVITAMBO         ZIMBABWE      <-3                  NA                0.3333333   0.0945115   0.5721551
24 months   ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              NA                0.4912281   0.3613034   0.6211527
24 months   ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              NA                0.2948718   0.2232386   0.3665050
24 months   ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               NA                0.2441860   0.1799129   0.3084592
24 months   ki1135781-COHORTS          INDIA         >=0                  NA                0.0492611   0.0320714   0.0664507
24 months   ki1135781-COHORTS          INDIA         <-3                  NA                0.5527950   0.4759855   0.6296046
24 months   ki1135781-COHORTS          INDIA         [-3--2)              NA                0.3060201   0.2690806   0.3429595
24 months   ki1135781-COHORTS          INDIA         [-2--1)              NA                0.2223572   0.2022666   0.2424479
24 months   ki1135781-COHORTS          INDIA         [-1-0)               NA                0.1120736   0.0976857   0.1264616
24 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.1926782   0.1587396   0.2266169
24 months   ki1135781-COHORTS          PHILIPPINES   <-3                  NA                0.5128205   0.3559168   0.6697243
24 months   ki1135781-COHORTS          PHILIPPINES   [-3--2)              NA                0.4848485   0.3995734   0.5701235
24 months   ki1135781-COHORTS          PHILIPPINES   [-2--1)              NA                0.3373702   0.2988168   0.3759237
24 months   ki1135781-COHORTS          PHILIPPINES   [-1-0)               NA                0.2596831   0.2341808   0.2851854


### Parameter: E(Y)


agecat      studyid                    country       intervention_level   baseline_level     estimate    ci_lower    ci_upper
----------  -------------------------  ------------  -------------------  ---------------  ----------  ----------  ----------
Birth       ki1126311-ZVITAMBO         ZIMBABWE      NA                   NA                0.0318872   0.0308152   0.0329592
3 months    ki1126311-ZVITAMBO         ZIMBABWE      NA                   NA                0.0571865   0.0553184   0.0590546
6 months    ki1126311-ZVITAMBO         ZIMBABWE      NA                   NA                0.0416213   0.0405321   0.0427105
6 months    ki1135781-COHORTS          INDIA         NA                   NA                0.0436033   0.0420422   0.0451643
6 months    ki1135781-COHORTS          PHILIPPINES   NA                   NA                0.0487988   0.0469207   0.0506769
9 months    ki1000108-CMC-V-BCS-2002   INDIA         NA                   NA                0.1284916   0.1197509   0.1372324
9 months    ki1101329-Keneba           GAMBIA        NA                   NA                0.0500874   0.0473282   0.0528466
9 months    ki1126311-ZVITAMBO         ZIMBABWE      NA                   NA                0.0479739   0.0471963   0.0487514
9 months    ki1135781-COHORTS          PHILIPPINES   NA                   NA                0.0719640   0.0697039   0.0742241
12 months   ki1000108-CMC-V-BCS-2002   INDIA         NA                   NA                0.2222222   0.2118579   0.2325866
12 months   ki1101329-Keneba           GAMBIA        NA                   NA                0.0686881   0.0654109   0.0719653
12 months   ki1126311-ZVITAMBO         ZIMBABWE      NA                   NA                0.0661120   0.0649957   0.0672284
12 months   ki1135781-COHORTS          INDIA         NA                   NA                0.1076923   0.1055047   0.1098799
12 months   ki1135781-COHORTS          PHILIPPINES   NA                   NA                0.1324686   0.1294171   0.1355200
18 months   ki1000108-CMC-V-BCS-2002   INDIA         NA                   NA                0.2936288   0.2800794   0.3071782
18 months   ki1000109-EE               PAKISTAN      NA                   NA                0.4870317   0.4717445   0.5023189
18 months   ki1101329-Keneba           GAMBIA        NA                   NA                0.0927070   0.0892168   0.0961973
18 months   ki1126311-ZVITAMBO         ZIMBABWE      NA                   NA                0.1745753   0.1712734   0.1778772
18 months   ki1135781-COHORTS          PHILIPPINES   NA                   NA                0.2509180   0.2475451   0.2542909
24 months   ki1000108-CMC-V-BCS-2002   INDIA         NA                   NA                0.3269231   0.3123817   0.3414645
24 months   ki1101329-Keneba           GAMBIA        NA                   NA                0.0836237   0.0801334   0.0871140
24 months   ki1126311-ZVITAMBO         ZIMBABWE      NA                   NA                0.2857143   0.2775654   0.2938632
24 months   ki1135781-COHORTS          INDIA         NA                   NA                0.1800041   0.1770476   0.1829607
24 months   ki1135781-COHORTS          PHILIPPINES   NA                   NA                0.2803661   0.2773169   0.2834152


### Parameter: RR


agecat      studyid                    country       intervention_level   baseline_level      estimate     ci_lower     ci_upper
----------  -------------------------  ------------  -------------------  ---------------  -----------  -----------  -----------
Birth       ki1126311-ZVITAMBO         ZIMBABWE      >=0                  >=0                 1.000000    1.0000000     1.000000
Birth       ki1126311-ZVITAMBO         ZIMBABWE      <-3                  >=0               122.095709   62.7267098   237.655730
Birth       ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              >=0                45.394482   23.2476231    88.639556
Birth       ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              >=0                10.533134    5.3342372    20.799021
Birth       ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               >=0                 2.517544    1.2251824     5.173129
3 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  >=0                 1.000000    1.0000000     1.000000
3 months    ki1126311-ZVITAMBO         ZIMBABWE      <-3                  >=0                54.216611   35.2350206    83.423844
3 months    ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              >=0                16.522917   10.5735108    25.819880
3 months    ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              >=0                 6.189739    3.9624568     9.668970
3 months    ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               >=0                 2.787173    1.7681668     4.393440
6 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  >=0                 1.000000    1.0000000     1.000000
6 months    ki1126311-ZVITAMBO         ZIMBABWE      <-3                  >=0                23.054245   14.6751991    36.217445
6 months    ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              >=0                10.869636    6.9713435    16.947808
6 months    ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              >=0                 4.221289    2.7168657     6.558763
6 months    ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               >=0                 1.716377    1.0866694     2.710991
6 months    ki1135781-COHORTS          INDIA         >=0                  >=0                 1.000000    1.0000000     1.000000
6 months    ki1135781-COHORTS          INDIA         <-3                  >=0                48.599998   19.9096811   118.633736
6 months    ki1135781-COHORTS          INDIA         [-3--2)              >=0                13.860000    5.6403893    34.057859
6 months    ki1135781-COHORTS          INDIA         [-2--1)              >=0                 5.815579    2.3689897    14.276535
6 months    ki1135781-COHORTS          INDIA         [-1-0)               >=0                 1.791610    0.6960027     4.611860
6 months    ki1135781-COHORTS          PHILIPPINES   >=0                  >=0                 1.000000    1.0000000     1.000000
6 months    ki1135781-COHORTS          PHILIPPINES   <-3                  >=0                27.087912   11.7718860    62.331132
6 months    ki1135781-COHORTS          PHILIPPINES   [-3--2)              >=0                10.902256    4.6964922    25.308075
6 months    ki1135781-COHORTS          PHILIPPINES   [-2--1)              >=0                 5.927572    2.6973274    13.026266
6 months    ki1135781-COHORTS          PHILIPPINES   [-1-0)               >=0                 2.679293    1.2074124     5.945452
9 months    ki1000108-CMC-V-BCS-2002   INDIA         >=0                  >=0                 1.000000    1.0000000     1.000000
9 months    ki1000108-CMC-V-BCS-2002   INDIA         <-3                  >=0                 5.583333    1.8996158    16.410482
9 months    ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              >=0                 4.020000    1.4696422    10.996146
9 months    ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              >=0                 2.061539    0.7913801     5.370290
9 months    ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               >=0                 1.016552    0.3672506     2.813821
9 months    ki1101329-Keneba           GAMBIA        >=0                  >=0                 1.000000    1.0000000     1.000000
9 months    ki1101329-Keneba           GAMBIA        <-3                  >=0                24.839989    8.9989592    68.566267
9 months    ki1101329-Keneba           GAMBIA        [-3--2)              >=0                13.799994    5.3327458    35.711402
9 months    ki1101329-Keneba           GAMBIA        [-2--1)              >=0                 4.668074    1.8371769    11.861087
9 months    ki1101329-Keneba           GAMBIA        [-1-0)               >=0                 1.704811    0.6416352     4.529645
9 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  >=0                 1.000000    1.0000000     1.000000
9 months    ki1126311-ZVITAMBO         ZIMBABWE      <-3                  >=0                10.632856    6.6349714    17.039657
9 months    ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              >=0                 6.187514    4.0076890     9.552970
9 months    ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              >=0                 4.306316    2.8840853     6.429893
9 months    ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               >=0                 1.812337    1.1974271     2.743019
9 months    ki1135781-COHORTS          PHILIPPINES   >=0                  >=0                 1.000000    1.0000000     1.000000
9 months    ki1135781-COHORTS          PHILIPPINES   <-3                  >=0                13.430769    7.1972792    25.063021
9 months    ki1135781-COHORTS          PHILIPPINES   [-3--2)              >=0                 8.127027    4.5069837    14.654717
9 months    ki1135781-COHORTS          PHILIPPINES   [-2--1)              >=0                 4.137867    2.3942168     7.151376
9 months    ki1135781-COHORTS          PHILIPPINES   [-1-0)               >=0                 1.847619    1.0572446     3.228861
12 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  >=0                 1.000000    1.0000000     1.000000
12 months   ki1000108-CMC-V-BCS-2002   INDIA         <-3                  >=0                 5.583333    2.1558492    14.460011
12 months   ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              >=0                 4.838888    2.0324633    11.520425
12 months   ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              >=0                 2.791666    1.2123752     6.428209
12 months   ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               >=0                 2.202948    0.9592882     5.058936
12 months   ki1101329-Keneba           GAMBIA        >=0                  >=0                 1.000000    1.0000000     1.000000
12 months   ki1101329-Keneba           GAMBIA        <-3                  >=0                10.090909    3.9462618    25.803267
12 months   ki1101329-Keneba           GAMBIA        [-3--2)              >=0                10.515790    5.1219534    21.589776
12 months   ki1101329-Keneba           GAMBIA        [-2--1)              >=0                 3.758465    1.8633493     7.581004
12 months   ki1101329-Keneba           GAMBIA        [-1-0)               >=0                 1.228216    0.5771337     2.613803
12 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  >=0                 1.000000    1.0000000     1.000000
12 months   ki1126311-ZVITAMBO         ZIMBABWE      <-3                  >=0                13.343253    8.3273638    21.380405
12 months   ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              >=0                 8.005952    5.1282907    12.498369
12 months   ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              >=0                 5.291761    3.4695633     8.070969
12 months   ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               >=0                 2.530537    1.6450904     3.892563
12 months   ki1135781-COHORTS          INDIA         >=0                  >=0                 1.000000    1.0000000     1.000000
12 months   ki1135781-COHORTS          INDIA         <-3                  >=0                44.190476   18.0771005   108.026073
12 months   ki1135781-COHORTS          INDIA         [-3--2)              >=0                23.744966    9.7797245    57.652281
12 months   ki1135781-COHORTS          INDIA         [-2--1)              >=0                15.310006    6.3397426    36.972524
12 months   ki1135781-COHORTS          INDIA         [-1-0)               >=0                 7.072401    2.9011583    17.240993
12 months   ki1135781-COHORTS          PHILIPPINES   >=0                  >=0                 1.000000    1.0000000     1.000000
12 months   ki1135781-COHORTS          PHILIPPINES   <-3                  >=0                 7.474688    4.5001816    12.415269
12 months   ki1135781-COHORTS          PHILIPPINES   [-3--2)              >=0                 6.090487    3.9577247     9.372564
12 months   ki1135781-COHORTS          PHILIPPINES   [-2--1)              >=0                 4.017325    2.7281699     5.915651
12 months   ki1135781-COHORTS          PHILIPPINES   [-1-0)               >=0                 1.980010    1.3360621     2.934324
18 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  >=0                 1.000000    1.0000000     1.000000
18 months   ki1000108-CMC-V-BCS-2002   INDIA         <-3                  >=0                 3.305556    1.6372181     6.673941
18 months   ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              >=0                 3.400000    1.8817408     6.143248
18 months   ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              >=0                 2.050794    1.1555783     3.639524
18 months   ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               >=0                 1.203196    0.6590988     2.196456
18 months   ki1000109-EE               PAKISTAN      >=0                  >=0                 1.000000    1.0000000     1.000000
18 months   ki1000109-EE               PAKISTAN      <-3                  >=0                 3.038095    1.5186061     6.077957
18 months   ki1000109-EE               PAKISTAN      [-3--2)              >=0                 3.142857    1.5901238     6.211812
18 months   ki1000109-EE               PAKISTAN      [-2--1)              >=0                 2.420849    1.2227574     4.792866
18 months   ki1000109-EE               PAKISTAN      [-1-0)               >=0                 1.687218    0.8281822     3.437293
18 months   ki1101329-Keneba           GAMBIA        >=0                  >=0                 1.000000    1.0000000     1.000000
18 months   ki1101329-Keneba           GAMBIA        <-3                  >=0                11.277778    4.6382096    27.421847
18 months   ki1101329-Keneba           GAMBIA        [-3--2)              >=0                10.488662    5.1412527    21.397904
18 months   ki1101329-Keneba           GAMBIA        [-2--1)              >=0                 4.958970    2.4997400     9.837578
18 months   ki1101329-Keneba           GAMBIA        [-1-0)               >=0                 2.098998    1.0369825     4.248666
18 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  >=0                 1.000000    1.0000000     1.000000
18 months   ki1126311-ZVITAMBO         ZIMBABWE      <-3                  >=0                 3.219696    1.8264697     5.675673
18 months   ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              >=0                 3.274268    2.0638756     5.194513
18 months   ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              >=0                 2.653783    1.7270745     4.077742
18 months   ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               >=0                 1.438235    0.9235187     2.239824
18 months   ki1135781-COHORTS          PHILIPPINES   >=0                  >=0                 1.000000    1.0000000     1.000000
18 months   ki1135781-COHORTS          PHILIPPINES   <-3                  >=0                 2.942986    1.9900612     4.352212
18 months   ki1135781-COHORTS          PHILIPPINES   [-3--2)              >=0                 3.095823    2.3868911     4.015314
18 months   ki1135781-COHORTS          PHILIPPINES   [-2--1)              >=0                 2.048400    1.6302031     2.573877
18 months   ki1135781-COHORTS          PHILIPPINES   [-1-0)               >=0                 1.432355    1.1463125     1.789776
24 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  >=0                 1.000000    1.0000000     1.000000
24 months   ki1000108-CMC-V-BCS-2002   INDIA         <-3                  >=0                 4.025000    1.9061501     8.499134
24 months   ki1000108-CMC-V-BCS-2002   INDIA         [-3--2)              >=0                 4.370000    2.3149249     8.249469
24 months   ki1000108-CMC-V-BCS-2002   INDIA         [-2--1)              >=0                 2.864151    1.5455150     5.307849
24 months   ki1000108-CMC-V-BCS-2002   INDIA         [-1-0)               >=0                 1.830612    0.9710867     3.450919
24 months   ki1101329-Keneba           GAMBIA        >=0                  >=0                 1.000000    1.0000000     1.000000
24 months   ki1101329-Keneba           GAMBIA        <-3                  >=0                 8.968421    3.6478187    22.049499
24 months   ki1101329-Keneba           GAMBIA        [-3--2)              >=0                 7.977528    3.9858950    15.966541
24 months   ki1101329-Keneba           GAMBIA        [-2--1)              >=0                 3.433753    1.7671424     6.672162
24 months   ki1101329-Keneba           GAMBIA        [-1-0)               >=0                 1.362848    0.6772873     2.742345
24 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  >=0                 1.000000    1.0000000     1.000000
24 months   ki1126311-ZVITAMBO         ZIMBABWE      <-3                  >=0                 2.037037    0.8010537     5.180077
24 months   ki1126311-ZVITAMBO         ZIMBABWE      [-3--2)              >=0                 3.001949    1.5608881     5.773444
24 months   ki1126311-ZVITAMBO         ZIMBABWE      [-2--1)              >=0                 1.801994    0.9448821     3.436602
24 months   ki1126311-ZVITAMBO         ZIMBABWE      [-1-0)               >=0                 1.492248    0.7763062     2.868461
24 months   ki1135781-COHORTS          INDIA         >=0                  >=0                 1.000000    1.0000000     1.000000
24 months   ki1135781-COHORTS          INDIA         <-3                  >=0                11.221739    7.7079862    16.337267
24 months   ki1135781-COHORTS          INDIA         [-3--2)              >=0                 6.212207    4.2942565     8.986776
24 months   ki1135781-COHORTS          INDIA         [-2--1)              >=0                 4.513852    3.1477675     6.472796
24 months   ki1135781-COHORTS          INDIA         [-1-0)               >=0                 2.275095    1.5686347     3.299720
24 months   ki1135781-COHORTS          PHILIPPINES   >=0                  >=0                 1.000000    1.0000000     1.000000
24 months   ki1135781-COHORTS          PHILIPPINES   <-3                  >=0                 2.661538    1.8698574     3.788410
24 months   ki1135781-COHORTS          PHILIPPINES   [-3--2)              >=0                 2.516364    1.9618700     3.227577
24 months   ki1135781-COHORTS          PHILIPPINES   [-2--1)              >=0                 1.750952    1.4193447     2.160033
24 months   ki1135781-COHORTS          PHILIPPINES   [-1-0)               >=0                 1.347755    1.1016091     1.648901


### Parameter: PAR


agecat      studyid                    country       intervention_level   baseline_level     estimate     ci_lower    ci_upper
----------  -------------------------  ------------  -------------------  ---------------  ----------  -----------  ----------
Birth       ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0290490    0.0269094   0.0311886
3 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0470155    0.0423925   0.0516384
6 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0293451    0.0243436   0.0343466
6 months    ki1135781-COHORTS          INDIA         >=0                  NA                0.0367445    0.0305529   0.0429362
6 months    ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0367298    0.0276454   0.0458143
9 months    ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.0538648   -0.0097507   0.1174802
9 months    ki1101329-Keneba           GAMBIA        >=0                  NA                0.0355946    0.0226819   0.0485074
9 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0310452    0.0247793   0.0373111
9 months    ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0461908    0.0331179   0.0592637
12 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.1326700    0.0634231   0.2019169
12 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.0416611    0.0239331   0.0593891
12 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0482682    0.0411052   0.0554311
12 months   ki1135781-COHORTS          INDIA         >=0                  NA                0.0990716    0.0912357   0.1069076
12 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0812318    0.0628098   0.0996538
18 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.1171582    0.0254178   0.2088987
18 months   ki1000109-EE               PAKISTAN      >=0                  NA                0.2749105    0.1343947   0.4154263
18 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.0644939    0.0459858   0.0830020
18 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.0865753    0.0512932   0.1218574
18 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0940914    0.0632862   0.1248966
24 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.1819955    0.0975580   0.2664331
24 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.0484124    0.0266867   0.0701382
24 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.1220779    0.0238620   0.2202939
24 months   ki1135781-COHORTS          INDIA         >=0                  NA                0.1307430    0.1133010   0.1481851
24 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.0876878    0.0536125   0.1217632


### Parameter: PAF


agecat      studyid                    country       intervention_level   baseline_level     estimate     ci_lower    ci_upper
----------  -------------------------  ------------  -------------------  ---------------  ----------  -----------  ----------
Birth       ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.9109918    0.8289406   0.9536859
3 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.8221423    0.7301078   0.8827927
6 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.7050497    0.5606467   0.8019915
6 months    ki1135781-COHORTS          INDIA         >=0                  NA                0.8427019    0.6229200   0.9343834
6 months    ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.7526790    0.4829482   0.8816992
9 months    ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.4192083   -0.3549102   0.7510396
9 months    ki1101329-Keneba           GAMBIA        >=0                  NA                0.7106504    0.3078670   0.8790360
9 months    ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.6471274    0.4903428   0.7556808
9 months    ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.6418600    0.4091865   0.7829023
12 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.5970149    0.1331487   0.8126588
12 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.6065254    0.2489957   0.7938464
12 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.7300965    0.5986059   0.8185128
12 months   ki1135781-COHORTS          INDIA         >=0                  NA                0.9199507    0.8083433   0.9665658
12 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.6132158    0.4481955   0.7288858
18 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.3990011   -0.0070907   0.6413434
18 months   ki1000109-EE               PAKISTAN      >=0                  NA                0.5644612    0.1579570   0.7747217
18 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.6956740    0.4197628   0.8403854
18 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.4959194    0.2482850   0.6619766
18 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.3749887    0.2398776   0.4860840
24 months   ki1000108-CMC-V-BCS-2002   INDIA         >=0                  NA                0.5566922    0.2116837   0.7507070
24 months   ki1101329-Keneba           GAMBIA        >=0                  NA                0.5789319    0.2247228   0.7713098
24 months   ki1126311-ZVITAMBO         ZIMBABWE      >=0                  NA                0.4272727   -0.0423451   0.6853091
24 months   ki1135781-COHORTS          INDIA         >=0                  NA                0.7263336    0.6119066   0.8070224
24 months   ki1135781-COHORTS          PHILIPPINES   >=0                  NA                0.3127619    0.1801202   0.4239446