# Эмнэлгийн удирдлагын системийн Use Case диаграмм

```mermaid
flowchart TB
    %% Actors
    Actor1(["Өвчтөн"])
    Actor2(["Админ"])
    Actor3(["Эмч"])
    Actor4(["Сувилагч"])
    Actor5(["Санхүүгийн\nажилтан"])
    
    %% Use cases - Өвчтөн
    UC1([" Систем хүлээн\nавах "])
    UC2([" Онолайх "])
    UC3([" Эмчилгээ\nзахиалах "])
    UC4([" Эмчилгээний түүх\nшинжлэх "])
    UC5([" Цаг авах "])
    UC14([" Төлбөр төлөх "])
    
    %% Use cases - Админ
    UC6([" Хүзээр\nтохируулах "])
    UC7([" Системийн\nтохиргоо хийх "])
    UC8([" Ажилтан бүртгэх "])
    
    %% Use cases - Эмч
    UC10([" Үйлчилгээ үзүүлэх "])
    UC12([" Өвчтөний мэдээлэл\nбүртгэх "])
    UC15([" Өвчтөний\nматериалтай\nбүртгэх "])
    
    %% Use cases - Сувилагч
    UC13([" Эмийн\nхүсэлт оруулах "])
    UC16([" Эмчид\nүзүүлэх "])
    
    %% Use cases - Санхүүгийн ажилтан
    UC9([" Төлбөр хүлээн\nавах "])
    UC11([" Тайлан гаргах "])
    UC17([" Эмийн\nүйлдвэрлэлийн\nбүртгэл "])
    
    %% Relationships - Өвчтөн
    Actor1 --- UC1
    Actor1 --- UC2
    Actor1 --- UC3
    Actor1 --- UC4
    Actor1 --- UC5
    Actor1 --- UC14
    
    %% Relationships - Админ
    Actor2 --- UC6
    Actor2 --- UC7
    Actor2 --- UC8
    
    %% Relationships - Эмч
    Actor3 --- UC10
    Actor3 --- UC12
    Actor3 --- UC15
    
    %% Relationships - Сувилагч
    Actor4 --- UC13
    Actor4 --- UC16
    
    %% Relationships - Санхүүгийн ажилтан
    Actor5 --- UC9
    Actor5 --- UC11
    Actor5 --- UC17
    
    %% Use case хоорондын холбоо (include)
    UC2 -.-> |include| UC1
    UC3 -.-> |include| UC2
    UC5 -.-> |include| UC2
    UC14 -.-> |include| UC5
    
    UC8 -.-> |include| UC7
    UC6 -.-> |include| UC7
    
    UC9 -.-> |include| UC10
    UC10 -.-> |include| UC12
    UC11 -.-> |include| UC9
    
    UC13 -.-> |include| UC12
    UC16 -.-> |include| UC13
    
    UC15 -.-> |include| UC10
    
    UC17 -.-> |include| UC11
    
    %% Use case хоорондын холбоо (extend)
    UC4 -.-> |extend| UC3
    UC11 -.-> |extend| UC9
    UC13 -.-> |extend| UC10
    
    %% Хоорондоо уялдаатай холбоос (dotted arrow)
    UC5 -..-> UC16
    UC16 -..-> UC10
