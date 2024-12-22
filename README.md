% Suspects
suspect(professor_plum).
suspect(miss_scarlet).
suspect(colonel_mustard).
suspect(mrs_white).
suspect(mr_green).
suspect(mrs_peacock).

% Weapons
weapon(candlestick).
weapon(knife).
weapon(revolver).
weapon(rope).
weapon(lead_pipe).
weapon(wrench).

% Locations
location(library).
location(kitchen).
location(ballroom).
location(conservatory).
location(study).
location(dining_room).

% Motives
motive(money).
motive(revenge).
motive(jealousy).
motive(inheritance).
motive(betrayal).
motive(power).

% Facts: Motive, Last Seen, and Used Weapon
suspect_motive(professor_plum, money).
suspect_motive(miss_scarlet, money).
suspect_motive(colonel_mustard, jealousy).
suspect_motive(mrs_white, power).
suspect_motive(mr_green, money).
suspect_motive(mrs_peacock, power).

last_seen(professor_plum, library).
last_seen(miss_scarlet, ballroom).
last_seen(colonel_mustard, ballroom).
last_seen(mrs_white, study).
last_seen(mr_green, study).
last_seen(mrs_peacock, dining_room).

used_weapon(professor_plum, lead_pipe).
used_weapon(miss_scarlet, knife).
used_weapon(colonel_mustard, revolver).
used_weapon(mrs_white, rope).
used_weapon(mr_green, lead_pipe).
used_weapon(mrs_peacock, wrench).

% Crime Details
crime_location(study).    
crime_weapon(lead_pipe). 
crime_motive(money).

% Rules
guilty(X) :-
    suspect(X),
    weapon(Y),
    location(Z),
    motive(A),
    suspect_motive(X, A),            
    last_seen(X, Z),           
    used_weapon(X, Y),       
    crime_location(Z),  
    crime_motive(A),
    crime_weapon(Y).      
