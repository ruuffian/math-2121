January 24th, 2023

## ABM- Agent Based Modeling

- Conway's Game of Life
	- Obvious
- Consumer Purchase Behavior
	- Agent: The Consumer
	- Atttributes: age, gender, income level, occupation
	- Provide reviews on products, suggest products to other consumers
	- Most important takeaway- figure out what the agent interactions actually do
- Disease Modeling
	- Agents: People Transmitting the Disease
	- Attributes: Age, Underlying Conditions, Vaccinated, etc ...
	- Environment: A locality that contains the agents
	- Interactions: Going to the store, public transportation, any intrapersonal interaction
	- Why?: Figure out how quickly diseases spread, why it spreads quicker in one place rather than another, etc
- Mass Shootings
	- Agents: Students/Teachers/Staff
	- Environment: A School, Possibly Temple
	- Interactions: Two students hiding together, a shooer with a student (fatality)
- How the Subway Spreads Influenza in NYC
	- Agents: Population of NYC
	- Environment: NYC - Manhattan, The Bronx, Statten Island, The Bronx, Brookyln
	- Attributes: Collected from Census
	- Interactions: Contact between agents at school or work, as well as contact with the subway
	- Conclusions: 4.4% of infections happened on the subway, similar risk as going to work- largest percentage of infections was going to school.

Massive Software - Agent Based Modeling to Choreograph Crowd Scenes
	- Generates realistic CGI crowd or creatures in order to simulate specific behavior
	- Allows each agent to be governed by different rules
	- Makes large crowd scenes much easier

## Mexican Wave

Basically just the Wave you see at sports games.
Note: Nobody is directing the wave, people react to the ones on their left/right
[MATLAB Code](link.md)

```MATLAB
% n: The number of agents
x = 1:n % [0,1,2,...,n];
% Consider a vector of n binary states instead-
x = 1:n==r % Where r is an integer, this will place 0s in every position and a 1 in the r-th position
```

Some other interesting things to note-
```MATLAB
% We right shift the vector x into xs and then compare each element of x to xs.
% We could've just looked at x(i) and x(i+1), but then we would have to deal with index errors.
x0 = x; % create a copy of state vector
xs = x([end 1:end-1]); % right-shifted copy of state vector
for i = 1:n % loop over state vector elements
	if x0(i)==0&&xs(i)==1 % if 0 & left neighbor 1,
		x(i) = 1; % become 1
	elseif x0(i)==1 % if 1,
		x(i) = 0; % become 0
	end
end
```

