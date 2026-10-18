# Optimal Satellite Formation Strategies

### **Results, simulations,  and code coming soon...**


Google's [Project Suncatcher](https://research.google/blog/exploring-a-space-based-scalable-ai-infrastructure-system-design/)
imagines solar-powered satellites flying in a tight cluster, close enough to communicate over short laser links.
We model that cluster: 81 satellites within about a kilometer of each other, neighbours 100-200 meters apart, 650 km above the Earth.

![One orbit of the cluster](docs/figures/orbital_plane_setup.gif)

*Left: the evolution of the cluster in the orbital plane over one orbit. Right: the same formation tilted out of that plane[^1]. 
Bottom: the distance between two highlighted neighbours. Each dot is a satellite and each grey line a laser link. 
At R_keep there is a collision risk between satellites (see next figure).*

[^1]: This enables along-track burns that don't collide with other satellites, at the extra cost of maintaining the tilt. 
The oscillations are a natural result of the orbital motion, requiring no fuel to maintain.

Satellites in this cluster must avoid space debris and keep their formation. In a large, spread-out constellation each
satellite can look after itself since its neighbours are tens of kilometers away. Here, the same small nudge to dodge debris
carries a satellite several times the initial spacing into its neighbours within a day, straight through the formation.

**Does a cluster this tight need to coordinate with its neighbours? What is the optimal coordination rule?**

![A sample of debris threat responses](docs/figures/debris_response.gif)

*Top frame: each threatened satellite dodges alone. 
Second: everyone moves together. Third: the formation shears, so each satellite moves by a different amount. Fourth: a local repulsive kernel is used.
Pc is the collision probability. Satellites within R_keep of each other are close enough to risk a collision at some point in the orbit.*
