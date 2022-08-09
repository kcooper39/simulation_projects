We wrote up a Jupyter notebook available here defining several functions in basic Python. They allow for flexible replication of the epidemic with a default of 10,000-run simulations. The most important function is update_kids() which takes a dictionary and an integer as parameters holding the “classroom” definition at any points and the number of infected kids at the beginning of the day. The “state of the classroom” at any point is defined by 21 kids each assigned with a binary health status (0 when healthy and 1 when sick) and a counter for the days elapsed since the initial infection. This counter is iterated upon until three days post-infection -- i.e. when “counter” is equal to 4. The function loops through the healthy kids and for each of those kids, realizes as many Bernoulli(p=0.02) trials as there are infectious kids (i.e., kids who have been infected and are within three days of the initial infection). The code uses the Python’s module random to generate PRNs for the Bernoulli trials.