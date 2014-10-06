Java-Profiling
==============
  HEAP   
   -> |perm|  young   |      old     |
      perm -> Dados permanentes
      young -> Espaçco menor e muitas coletas GC mais rápidas. Não sofre compactação e os objetos são simplesmente copiados     para as outras áreas. Isso torma a coleta eficiente.
        - Dividida em S0, S1 e Eden; Onde o S0 e S1 são áreas temporárias de objetos; A EDEN é onde os objetos são criados       pela primeira vez.
      old -> Espaçco maior e poucas coletas GC mais demorada
      
  GC
  
  JMC - Java Mission Control (http://docs.oracle.com/javase/7/docs/technotes/guides/jmc/)
    Requirements:
      - JDK1.7.0_67 or later
            /bin/jmc.ini 
                
            /bin/jmc (sh)
    
  JPS - Java Virtual Machine Proccess Status Tool
    Requirements:
      - JDK
          /bin/jps
            jps -mlv <pid>
    
  JINFO - Java Virtual Machine Configuration Info
    Requirements:
      - JDK
          /bin/jinfo
            jinfo <pid>
            
  JMAP - Java Virtual Machine Memory Map
    Requirements:
      - JDK
          /bin/jmap   [-histo:live | -heap | -dump ]
            jmap <pid> {$jmap -dump:live,format=b,file=arquivo.hprof (ou .bin) <pid>}
            
    JHAT - Java Heap Analysis Tool
    Requirements:
      - JDK
          /bin/jhat
            jhat -J-Xmx256m arquivo.hprof 
            
  JSTAT - Java Virtual Machine Statistics Monitoring Tools
    Requirements:
      - JDK
          /bin/jstat 
            jstat -gccause <pid> [-class | -gc | -gcutil | -gcoldcapacity]
            
  JSTACK - Java Stack Trace Threads
    Requirements:
      - JDK
          /bin/jstack
            jstack <pid> 
            
 JDB - Java Debug
    Requirements:
      - JDK
          /bin/jdb
            jdb <class> 
            
  
            
