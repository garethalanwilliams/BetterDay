BetterDay Backlog

Last updated for v3.3.1

Priority definitions:

-   P0 — blocks reliable behaviour or learning; fix before progressing
-   P1 — important next-iteration work
-   P2 — worthwhile improvement, not blocking the current foundation
-   Future — intentionally deferred

  ---------------------------------------------------------------------------
  ID                Priority          Item                  Status
  ----------------- ----------------- --------------------- -----------------
  BD-001            P0                Historical data must  ✅ Closed
                                      remain separate from  
                                      today’s data          

  BD-002            P0                Unknown/missing data  ✅ Closed
                                      must not be treated   
                                      as negative or zero   

  BD-003            P0                Poor recovery must    ✅ Closed
                                      materially change     
                                      Today’s Focus         

  BD-029            P0                Movement completion   🧪 Fixed v3.3.1;
                                      must be reflected on  regression retest
                                      Today rather than     required
                                      continuing to show    
                                      only the plan         

  BD-004            P1                Refine system-like    Backlog
                                      recovery and          
                                      recommendation copy   

  BD-005            P1                Improve automatic     Backlog
                                      food classification;  
                                      move from prototype   
                                      keyword rules toward  
                                      AI classification     

  BD-006            P1                Formalise logged-day  In progress via
                                      and                   v3.3 foundation
                                      domain-completeness   
                                      rules                 

  BD-007            P1                Handle                In progress
                                      incomplete/missing    
                                      days without          
                                      distorting learning   

  BD-008            P1                Implement             Designed;
                                      insight-confidence    implementation
                                      model: insufficient / pending
                                      tentative / emerging  
                                      / established         

  BD-009            P1                Improve               Backlog
                                      emerging-insight      
                                      wording and evidence  
                                      transparency          

  BD-010            P1                Handle contradictory  Designed;
                                      recovery signals      implementation
                                      explicitly            pending

  BD-011            P1                Implement alcohol →   Planned for
                                      next-day              Learning Engine
                                      sleep/recovery        
                                      evidence              
                                      relationships         

  BD-012            P1                AI should choose one  Designed;
                                      primary               implementation
                                      recommendation when   pending
                                      several candidates    
                                      exist                 

  BD-030            P1                Greeting should       🧪 Fixed v3.3.1;
                                      reflect local time:   regression retest
                                      morning / afternoon / required
                                      evening               

  BD-013            P2                Plain-English “Why    Backlog
                                      this rating?” for     
                                      food rather than      
                                      technical NOVA        
                                      presentation          

  BD-014            P2                Allow                 Backlog
                                      editing/deleting logs 

  BD-015            P2                Personalise           Backlog
                                      weekly-review         
                                      headline              

  BD-016            P2                Follow up previous    Backlog
                                      week’s recommendation 

  BD-017            P2                Previous              Backlog
                                      weekly-review history 

  BD-018            P2                Week-on-week          Backlog
                                      comparison            

  BD-019            P2                Longer-term personal  Backlog
                                      relationships         

  BD-020            P2                More personalised     Backlog
                                      hydration guidance    

  BD-021            P2                Historical-day        Backlog
                                      editing and           
                                      recalculation rules   

  BD-022            P2                “Explain this         Backlog
                                      insight” capability   

  BD-028            P2                Visible prototype     ✅ Complete
                                      version in test menu  

  BD-031            P2                Hydration Today tile  Backlog
                                      currently mixes state 
                                      and advice; consider  
                                      a more state-like     
                                      label                 

  BD-032            P2                Improve visual        Backlog
                                      distinction between   
                                      planned, partly       
                                      completed and         
                                      completed movement    

  BD-023            Future            Photo-based food      Deferred
                                      analysis              

  BD-024            Future            Wearable integrations Deferred
                                      such as Garmin /      
                                      Apple Health          

  BD-025            Future            Proper account/data   Deferred
                                      persistence beyond    
                                      browser local storage 

  BD-026            Future            Accessibility review  Pre-release

  BD-027            Future            Device/browser test   Pre-release
                                      matrix                
  ---------------------------------------------------------------------------

Learning Engine v1 data-model changes

The current implementation direction is to preserve the lightweight UI
while adding structured evidence underneath:

1.  Timestamp food, hydration, movement and alcohol events
    automatically.
2.  Store domain-specific completeness / unknown state.
3.  Keep alcohol unknown until explicitly selected, including an
    explicit None.
4.  Store actual movement outcome separately from the morning movement
    plan.
5.  Store food-classification confidence and whether the user corrected
    the estimate.
6.  Produce structured Daily Observation and Recovery Observation
    objects.
7.  Build candidate trends only from comparable, sufficiently complete
    observations.

Regression status

v3.3 checks passed before patch

-   Clean Today starts with unknown/unlogged states
-   Morning check-in produces sensible recovery
-   Missing food/hydration remain unknown after check-in
-   Food persists across navigation
-   Today recommendation updates after food is logged
-   Hydration total persists and recommendation changes appropriately

v3.3 defects found

-   Movement completion selected on Log was not reflected on Today →
    BD-029
-   Static “Good morning” displayed in late afternoon → BD-030

Both were patched in v3.3.1 and need targeted regression confirmation
before the remaining suite continues.
