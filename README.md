<h3>The code you have provided appears to be calculating a variety of metrics related to customer service agents, such as attendance rate, schedule adherence, and skillset proficiency. These metrics can be useful for understanding the performance of individual agents or for comparing the performance of different agents or teams. Some of the metrics you are calculating, such as average handle time and average wait time, can also be useful for understanding the customer experience and for identifying areas for improvement.</h3>

<H4>
  data.csv content :
  
</H4>
<table>
  <tr>
<th> ID agent</th>
<th> abandonment rate</th>
<th> agent absenteeism rate</th>
<th> agent attendance rate</th>
<th> attendance by time</th>
<th> availability rate</th>
<th> certification rate</th>
<th> productivity by time</th>
<th> satisfaction score</th>
<th> schedule adherence</th>
<th> schedule adherence by time</th>
<th> schedule efficiency</th>
<th> schedule efficiency by time</th>
<th> schedule flexibility</th>
<th> schedule flexibility by time</th>
<th> skillset diversity</th>
<th> skillset effectiveness</th>
<th> skillset proficiency</th>
<th> skillset utilization</th>
<th> training completion rate</th>
<th> turnover rate</th>
<th> turnover rate by reason</th>
<th> turnover rate by time</th>
<th> utilization rate</th>
<th> average acw time by reason</th>
<th> average acw time by time</th>
<th> average wait time</th>
<th> average wait time by time</th>
<th> average handle time</th>
<th> average handle time by reason</th>
<th> average handle time by time</th>
<th> average hold time</th>
<th> average hold time by reason</th>
<th> average hold time by time</th>
<th> average queue time by reason</th>
<th> average queue time by time</th>
<th> average speed to answer</th>
<th> average speed to answer by time</th>
<th> average talk time</th>
<th> average talk time by reason</th>
<th> average talk time by time</th>
<th> average time in acw</th>
<th> average time in acw by reason</th>
<th> average time in acw by time</th>
<th> average time in queue</th>
<th> average time in queue before abandoning</th>
<th> average time in queue before abandoning by reason</th>
<th> average time in queue before abandoning by</th>
</tr>
</table>
 
### Import necessary modules
```python:import pandas as pd 
import numpy as np```

### Read in data

```python: data = pd.read_csv("data.csv")```
### Calculate abandonment rate

```python: abandonment_rate = data[data["status"] == "abandoned"].count() / data["status"].count()```
### Calculate agent absenteeism rate

```python: agent_absenteeism_rate = data[data["absent"] == 1].count() / data["absent"].count()```
### Calculate agent attendance rate

```python: agent_attendance_rate = data[data["attended"] == 1].count() / data["attended"].count()```
### Calculate agent attendance rate by time of day

```python: attendance_by_time = data.groupby("time_of_day")["attended"].mean()```
### Calculate agent availability rate

```python: availability_rate = data[data["available"] == 1].count() / data["available"].count()```
### Calculate agent certification rate

```python: certification_rate = data[data["certified"] == 1].count() / data["certified"].count()```
### Calculate agent productivity by time of day

```python: productivity_by_time = data.groupby("time_of_day")["productivity"].mean()```
### Calculate agent satisfaction score

```python: satisfaction_score = data["satisfaction"].mean()```
### Calculate agent schedule adherence

```python: schedule_adherence = data[data["adhered_to_schedule"] == 1].count() / data["adhered_to_schedule"].count()```
### Calculate agent schedule adherence by time of day

```python: schedule_adherence_by_time = data.groupby("time_of_day")["adhered_to_schedule"].mean()```
### Calculate agent schedule efficiency

```python: schedule_efficiency = data["scheduled_time"].sum() / data["actual_time"].sum()```
### Calculate agent schedule efficiency by time of day

```python: schedule_efficiency_by_time = data.groupby("time_of_day")["scheduled_time"].sum() / data.groupby("time_of_day")["actual_time"].sum()```
### Calculate agent schedule flexibility

```python: schedule_flexibility = data[data["schedule_changes"] > 0].count() / data["schedule_changes"].count()```
### Calculate agent schedule flexibility by time of day

```python: schedule_flexibility_by_time = data.groupby("time_of_day")["schedule_changes"].mean()```
### Calculate agent skillset diversity

```python: skillset_diversity = data["skillset"].nunique() / data["skillset"].count()```
### Calculate agent skillset effectiveness

```python: skillset_effectiveness = data[data["effective_use_of_skillset"] == 1].count() / data["effective_use_of_skillset"].count()```
### Calculate agent skillset proficiency

```python: skillset_proficiency = data["skillset_proficiency"].mean()```
### Calculate agent skillset utilization

```python: skillset_utilization = data[data["utilized_skillset"] == 1].count() / data["utilized_skillset"].count()```
### Calculate agent training completion rate

```python: training_completion_rate = data[data["training_completed"] == 1].count() / data["training_completed"].count()```
### Calculate agent turnover rate

```python: turnover_rate = data[data["left_company"] == 1].count() / data["left_company"].count()```
### Calculate agent turnover rate by reason

```python: turnover_rate_by_reason = data.groupby("reason_for_leaving")["left_company"].mean()```
### Calculate agent turnover rate by time of day

```python: turnover_rate_by_time = data.groupby("time_of_day")["left_company"].mean()```
### Calculate agent utilization rate

```python: utilization_rate = data[data["utilized"] == 1].count() / data["utilized"].count()```
### Calculate average after call work time by reason

```python: average_acw_time_by_reason = data.groupby("call_reason")["after_call_work_time"].mean()```
### Calculate average after call work time by time of day

```python: average_acw_time_by_time = data.groupby("time_of_day")["after_call_work_time"].mean()```
### Calculate average call wait time

```python: average_wait_time = data["wait_time"].mean()```
### Calculate average call wait time by time of day

```python: average_wait_time_by_time = data.groupby("time_of_day")["wait_time"].mean()```
### Calculate average handle time

```python: average_handle_time = data["handle_time"].mean()```
### Calculate average handle time by reason

```python: average_handle_time_by_reason = data.groupby("call_reason")["handle_time"].mean()```
### Calculate average handle time by time of day

```python: average_handle_time_by_time = data.groupby("time_of_day")["handle_time"].mean()```
### Calculate average hold time

```python: average_hold_time = data["hold_time"].mean()```
### Calculate average hold time by reason

```python: average_hold_time_by_reason = data.groupby("call_reason")["hold_time"].mean()```
### Calculate average hold time by time of day

```python: average_hold_time_by_time = data.groupby("time_of_day")["hold_time"].mean()```
### Calculate average queue time by reason

```python: average_queue_time_by_reason = data.groupby("call_reason")["queue_time"].mean()```
### Calculate average speed to answer

```python: average_speed_to_answer = data["speed_to_answer"].mean()```
### Calculate average speed to answer by time of day

```python: average_speed_to_answer_by_time = data.groupby("time_of_day")["speed_to_answer"].mean()```
### Calculate average talk time

```python: average_talk_time = data["talk_time"].mean()```
### Calculate average talk time by reason

```python: average_talk_time_by_reason = data.groupby("call_reason")["talk_time"].mean()```
### Calculate average talk time by time of day

```python: average_talk_time_by_time = data.groupby("time_of_day")["talk_time"].mean()```
### Calculate average time in after call work

```python: average_time_in_acw = data["after_call_work_time"].mean()```
### Calculate average time in after call work by reason

```python: average_time_in_acw_by_reason = data.groupby("call_reason")["after_call_work_time"].mean()```
### Calculate average time in after call work by time of day

```python: average_time_in_acw_by_time = data.groupby("time_of_day")["after_call_work_time"].mean()```
### Calculate average time in queue

```python: average_time_in_queue = data["queue_time"].mean()```
### Calculate average time in queue before abandoning

```python: average_time_in_queue_before_abandoning = data[data["status"] == "abandoned"]["queue_time"].mean()```
### Calculate average time in queue before abandoning by reason

```python: average_time_in_queue_before_abandoning_by_reason = data[data["status"] == "abandoned"].groupby("call_reason")["queue_time"].mean()```
### Calculate average time in queue before abandoning by time of day

```python: average_time_in_queue_before_abandoning_by_time = data[data["status"] == "abandoned"].groupby("time_of_day")["queue_time"].mean()```
### Calculate average time in queue before disconnecting

```python: average_time_in_queue_before_disconnecting = data[data["status"] == "disconnected"]["queue_time"].mean()```
### Calculate average time in queue before disconnecting by reason

```python: average_time_in_queue_before_disconnecting_by_reason = data[data["status"] == "disconnected"].groupby("call_reason")["queue_time"].mean()```
### Calculate average time in queue before disconnecting by time of day

```python: average_time_in_queue_before_disconnecting_by_time = data[data["status"] == "disconnected"].groupby("time_of_day")["queue_time"].mean()```
### Calculate average time in queue before transferring

```python: average_time_in_queue_before_transferring = data[data["status"] == "transferred"]["queue_time"].mean()```
### Calculate average time in queue before transferring by reason

```python: average_time_in_queue_before_transferring_by_reason = data[data["status"] == "transferred"].groupby("call_reason")["queue_time"].mean()```
### Calculate average time in queue before transferring by time of day

```python: average_time_in_queue_before_transferring_by_time = data[data["status"] == "transferred"].groupby("time_of_day")["queue_time"].mean()```
### Calculate average wrap-up time

```python: average_wrap_up_time = data["wrap_up_time"].mean()```
### Calculate average wrap-up time by reason

```python: average_wrap_up_time_by_reason = data.groupby("call_reason")["wrap_up_time"].mean()```
### Calculate average wrap-up time by time of day

```python: average_wrap_up_time_by_time = data.groupby("time_of_day")["wrap_up_time"].mean()```
### Calculate call abandonment rate by reason

```python: call_abandonment_rate_by_reason = data[data["status"] == "abandoned"].groupby("call_reason").count() / data.groupby("call_reason").count()```
### Calculate call abandonment rate by time of day

```python: call_abandonment_rate_by_time = data[data["status"] == "abandoned"].groupby("time_of_day").count() / data.groupby("time_of_day").count()```
### Calculate call back rate

```python: call_back_rate = data[data["call_back_requested"] == 1].count() / data["call_back_requested"].count()```
### Calculate call back rate by time of day

```python: call_back_rate_by_time = data[data["call_back_requested"] == 1].groupby("time_of_day").count() / data.groupby("time_of_day").count()```
### Calculate customer effort score

```python: customer_effort_score = data["customer_effort"].mean()```
### Calculate customer satisfaction by reason

```python: customer_satisfaction_by_reason = data.groupby("call_reason")["customer_satisfaction"].mean()```
### Calculate customer satisfaction score

```python: customer_satisfaction_score = data["customer_satisfaction"].mean()```
### Calculate first call resolution rate

```python: first_call_resolution_rate = data[data["first_call_resolution"] == 1].count() / data["first_call_resolution"].count()```
### Calculate first call resolution rate by reason

```python: first_call_resolution_rate_by_reason = data[data["first_call_resolution"] == 1].groupby("call_reason").count() / data.groupby("call_reason").count()```
### Calculate net promoter score

```python: net_promoter_score = data["net_promoter_score"].mean()```
### Calculate net promoter score by reason

```python: net_promoter_score_by_reason = data.groupby("call_reason")["net_promoter_score"].mean()```
### Calculate net promoter score by time of day

```python: net_promoter_score_by_time = data.groupby("time_of_day")["net_promoter_score"].mean()```
### Calculate quality assurance score

```python: quality_assurance_score = data["quality_assurance_score"].mean()```
### Calculate service level

```python: service_level = data[data["call_answer_time"] <= data["service_level_goal"]].count() / data["call_answer_time"].count()```
### Calculate service level by reason

```python: service_level_by_reason = data[data["call_answer_time"] <= data["service_level_goal"]].groupby("call_reason").count() / data.groupby("call_reason").count()```
### Calculate service level by time of day

```python: service_level_by_time = data[data["call_answer_time"] <= data["service_level_goal"]].groupby("time_of_day").count() / data.groupby("time_of_day").count()```
### Calculate call center training budget

```python: training_budget = data["training_cost"].sum()```
### Calculate call center training churn rate

```python: training_churn_rate = data[data["left_company_after_training"] == 1].count() / data["left_company_after_training"].count()```
### Calculate call center training cost per agent

```python: training_cost_per_agent = data["training_cost"].sum() / data["agent_id"].nunique()```
### Calculate call center training cost per day

```python: training_cost_per_day = data["training_cost"].sum() / data["training_days"].sum()```
### Calculate call center training cost per hour

```python: training_cost_per_hour = data["training_cost"].sum() / (data["training_days"].sum() * 8)```
### Calculate call center training cost per month

```python: training_cost_per_month = data["training_cost"].sum() / (data["training_days"].sum() / 30)```
### Calculate call center training cost per week

```python: training_cost_per_week = data["training_cost"].sum() / (data["training_days"].sum() / 7)```
### Calculate call center training cost per year

```python: training_cost_per_year = data["training_cost"].sum() / (data["training_days"].sum() / 365)```
### Calculate call center training effectiveness

```python: training_effectiveness = data[data["training_effective"] == 1].count() / data["training_effective"].count()```
### Calculate call center training efficiency

```python: training_efficiency = data["training_days"].sum() / data["agent_id"].nunique()```
###  Calculate the number of agents who completed training

```python: training_completed = data[data["training_completed"] == 1].count()```
###  Calculate the number of agents who left the company after training

```python: training_churn = data[(data["training_completed"] == 1) & (data["left_company"] == 1)].count()```
###  Calculate the training retention rate

```python: training_retention_rate = 1 - (training_churn / training_completed)```
### Calculate call resolution rate

```python: call_resolution_rate = data[data["status"] == "resolved"].count() / data["status"].count()```
### Calculate call resolution rate by time of day

```python: call_resolution_rate_by_time = data[data["status"] == "resolved"].groupby("time_of_day").count() / data.groupby("time_of_day").count()```
### Calculate call routing efficiency

```python: call_routing_efficiency = data[data["call_routed_correctly"] == 1].count() / data["call_routed_correctly"].count()```
### Calculate call routing efficiency by time of day

```python: call_routing_efficiency_by_time = data[data["call_routed_correctly"] == 1].groupby("time_of_day").count() / data.groupby("time_of_day").count()```
### Calculate call transfer rate

```python: call_transfer_rate = data[data["status"] == "transferred"].count() / data["status"].count()```
### Calculate call transfer rate by time of day

```python: call_transfer_rate_by_time = data[data["status"] == "transferred"].groupby("time_of_day").count() / data.groupby("time_of_day").count()```
### Calculate call center revenue retention rate

```python: revenue_retention_rate = data[data["revenue_retained"] == 1].count() / data["revenue_retained"].count()```
### Calculate call center revenue retention rate by reason

```python: revenue_retention_rate_by_reason = data[data["revenue_retained"] == 1].groupby("call_reason").count() / data.groupby("call_reason").count()```
### Calculate call center revenue retention rate by time of day

```python: revenue_retention_rate_by_time = data[data["revenue_retained"] == 1].groupby("time_of_day").count() / data.groupby("time_of_day").count()```
### Calculate call center capacity utilization rate

```python: capacity_utilization_rate = data["call_count"].sum() / (data["agent_id"].nunique() * data["hours_of_operation"].max())```
### Calculate call center cost per agent

```python: cost_per_agent = data["agent_cost"].sum() / data["agent_id"].nunique()```
### Calculate call center cost per call

```python: cost_per_call = data["call_cost"].sum() / data["call_count"].sum()```
### Calculate call center cost per agent by reason

```python: cost_per_agent_by_reason = data.groupby("call_reason")["agent_cost"].sum() / data.groupby("call_reason")["agent_id"].nunique()```
### Calculate call center cost per agent by time of day

```python: cost_per_agent_by_time = data.groupby("time_of_day")["agent_cost"].sum() / data.groupby("time_of_day")["agent_id"].nunique()```
### Calculate call center cost per call

```python: cost_per_call = data["call_cost"].sum() / data["call_count"].sum()```
### Calculate call center cost per call by reason

```python: cost_per_call_by_reason = data.groupby("call_reason")["call_cost"].sum() / data.groupby("call_reason")["call_count"].sum()```
### Calculate call center cost per call by time of day

```python: cost_per_call_by_time = data.groupby("time_of_day")["call_cost"].sum() / data.groupby("time_of_day")["call_count"].sum()```
### Calculate call center cost per contact

```python: cost_per_contact = data["contact_cost"].sum() / data["contact_count"].sum()```
### Calculate call center cost per contact by reason

```python: cost_per_contact_by_reason = data.groupby("call_reason")["contact_cost"].sum() / data.groupby("call_reason")["contact_count"].sum()```
### Calculate call center cost per contact by time of day

```python: cost_per_contact_by_time = data.groupby("time_of_day")["contact_cost"].sum() / data.groupby("time_of_day")["contact_count"].sum()```
### Calculate call center cost per customer

```python: cost_per_customer = data["customer_cost"].sum() / data["customer_count"].sum()```
### Calculate call center revenue per week

```python: revenue_per_week = data["revenue"].sum() / (data["week"].nunique())```
### Calculate call center revenue per week by reason

```python: revenue_per_week_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["week"].nunique()```
### Calculate call center revenue per week by time of day

```python: revenue_per_week_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["week"].nunique()```
### Calculate call center revenue per year

```python: revenue_per_year = data["revenue"].sum() / (data["year"].nunique())```
### Calculate call center revenue per year by reason

```python: revenue_per_year_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["year"].nunique()```
### Calculate call center revenue per year by time of day

```python: revenue_per_year_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["year"].nunique()```
### Calculate call center revenue per minute

```python: revenue_per_minute = data["revenue"].sum() / (data["call_duration"].sum() / 60)```
### Calculate call center revenue per minute by reason

```python: revenue_per_minute_by_reason = data.groupby("call_reason")["revenue"].sum() / (data.groupby("call_reason")["call_duration"].sum() / 60)```
### Calculate call center revenue per minute by time of day

```python: revenue_per_minute_by_time = data.groupby("time_of_day")["revenue"].sum() / (data.groupby("time_of_day")["call_duration"].sum() / 60)```
### Calculate call center revenue per month

```python: revenue_per_month = data["revenue"].sum() / (data["month"].nunique())```
### Calculate call center revenue per month by reason

```python: revenue_per_month_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["month"].nunique()```
### Calculate call center revenue per month by time of day

```python: revenue_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["duration"].count()```
### Calculate call center revenue per hour

```python: revenue_per_hour = data["revenue"].sum() / (data["hours_of_operation"].max())```
### Calculate call center revenue per hour by reason

```python: revenue_per_hour_by_reason = data.groupby("call_reason")["revenue"].sum() / (data.groupby("call_reason")["hours_of_operation"].max())```
### Calculate call center revenue per hour by time of day

```python: revenue_per_hour_by_time = data.groupby("time_of_day")["revenue"].sum() / (data.groupby("time_of_day")["hours_of_operation"].max())```
### Calculate call center revenue per interaction

```python: revenue_per_interaction = data["revenue"].sum() / data["interaction_count"].sum()```
### Calculate call center revenue per interaction by reason

```python: revenue_per_interaction_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["interaction_count"].sum()```
### Calculate call center revenue per interaction by time of day

```python: revenue_per_interaction_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["interaction_count"].sum()```
### Calculate call center revenue per customer

```python: revenue_per_customer = data["revenue"].sum() / data["customer_count"].sum()```
### Calculate call center revenue per customer by reason

```python: revenue_per_customer_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["customer_count"].sum()```
### Calculate call center revenue per customer by time of day

```python: revenue_per_customer_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["customer_count"].sum()```
### Calculate call center revenue per day

```python: revenue_per_day = data["revenue"].sum() / data["day"].nunique()```
### Calculate call center revenue per day by reason

```python: revenue_per_day_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["day"].nunique()```
### Calculate call center revenue per call

```python: revenue_per_call = data["revenue"].sum() / data["call_count"].sum()```
### Calculate call center revenue per call by reason

```python: revenue_per_call_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["call_count"].sum()```
### Calculate call center revenue per call by time of day

```python: revenue_per_call_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["call_count"].sum()```
### Calculate call center revenue per contact

```python: revenue_per_contact = data["revenue"].sum() / data["contact_count"].sum()```
### Calculate call center revenue per contact by reason

```python: revenue_per_contact_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["contact_count"].sum()```
### Calculate call center revenue per contact by time of day

```python: revenue_per_contact_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["contact_count"].sum()```
### Calculate call center cost per customer by reason

```python: cost_per_customer_by_reason = data.groupby("call_reason")["cost"].sum() / data.groupby("call_reason")["customer_count"].sum()```
### Calculate call center cost per customer by time of day

```python: cost_per_customer_by_time = data.groupby("time_of_day")["cost"].sum() / data.groupby("time_of_day")["customer_count"].sum()```
### Calculate call center cost per day

```python: cost_per_day = data["cost"].sum() / data["day"].nunique()```
### Calculate call center cost per day by reason

```python: cost_per_day_by_reason = data.groupby("call_reason")["cost"].sum() / data.groupby("call_reason")["day"].nunique()```
### Calculate call center cost per day by time of day

```python: cost_per_day_by_time = data.groupby("time_of_day")["cost"].sum() / data.groupby("time_of_day")["day"].nunique()```
### Calculate call center cost per minute

```python: cost_per_minute = data["cost"].sum() / (data["call_duration"].sum() / 60)```
### Calculate call center cost per minute by reason

```python: cost_per_minute_by_reason = data.groupby("call_reason")["cost"].sum() / (data.groupby("call_reason")["call_duration"].sum() / 60)```
### Calculate call center cost per minute by time of day

```python: cost_per_minute_by_time = data.groupby("time_of_day")["cost"].sum() / (data.groupby("time_of_day")["call_duration"].sum() / 60)```
### Calculate call center cost per month

```python: cost_per_month = data["cost"].sum() / data["month"].nunique()```
### Calculate call center cost per month by reason

```python: cost_per_month_by_reason = data.groupby("call_reason")["cost"].sum() / data.groupby("call_reason")["month"].nunique()```
### Calculate call center cost per month by time of day

```python: cost_per_month_by_time = data.groupby("time_of_day")["cost"].sum() / data.groupby("time_of_day")["month"].nunique()```
### Calculate call center cost savings

```python: cost_savings = data["initial_cost"].sum() - data["cost"].sum()```
### Calculate call center cost savings by reason

```python: cost_savings_by_reason = data.groupby("call_reason")["initial_cost"].sum() - data.groupby("call_reason")["cost"].sum()```
### Calculate call center cost savings by time of day

```python: cost_savings_by_time = data.groupby("time_of_day")["initial_cost"].sum() - data.groupby("time_of_day")["cost"].sum()```
### Calculate call center efficiency rate

```python: efficiency_rate = (data["call_count"].sum() / data["hours_of_operation"].max()) / data["agent_count"].max()```
### Calculate call center efficiency rate by reason

```python: efficiency_rate_by_reason = (data.groupby("call_reason")["call_count"].sum() / data.groupby("call_reason")["hours_of_operation"].max()) / data.groupby("call_reason")["agent_count"].max()```
### Calculate call center efficiency rate by time of day

```python: efficiency_rate_by_time = (data.groupby("time_of_day")["call_count"].sum() / data.groupby("time_of_day")["hours_of_operation"].max()) / data.groupby("time_of_day")["agent_count"].max()```
### Calculate call center occupancy rate

```python: occupancy_rate = (data["hours_of_operation"].max() - data["idle_time"].sum()) / data["hours_of_operation"].max()```
### Calculate call center performance index

```python: performance_index = (data["call_count"].sum() / data["hours_of_operation"].max()) * data["satisfaction_score"].mean()```
### Calculate call center performance index by reason

```python: performance_index_by_reason = (data.groupby("call_reason")["call_count"].sum() / data.groupby("call_reason")["hours_of_operation"].max()) * data.groupby("call_reason")["satisfaction_score"].mean()```
### Calculate call center performance index by time of day

```python: performance_index_by_time = (data.groupby("time_of_day")["call_count"].sum() / data.groupby("time_of_day")["hours_of_operation"].max()) * data.groupby("time_of_day")["satisfaction_score"].mean()```
### Calculate call center productivity rate

```python: productivity_rate = data["call_count"].sum() / (data["hours_of_operation"].max() * data["agent_count"].max())```
### Calculate call center productivity rate by reason

```python: productivity_rate_by_reason = data.groupby("call_reason")["call_count"].sum() / (data.groupby("call_reason")["hours_of_operation"].max() * data.groupby("call_reason")["agent_count"].max())```
### Calculate call center productivity rate by time of day

```python: productivity_rate_by_time = data.groupby("time_of_day")["call_count"].sum() / (data.groupby("time_of_day")["hours_of_operation"].max() * data.groupby("time_of_day")["agent_count"].max())```
### Calculate call center revenue churn rate

```python: revenue_churn_rate = (data["initial_revenue"].sum() - data["revenue"].sum()) / data["initial_revenue"].sum()```
### Calculate call center revenue churn rate by reason

```python: revenue_churn_rate_by_reason = (data.groupby("call_reason")["initial_revenue"].sum() - data.groupby("call_reason")["revenue"].sum()) / data.groupby("call_reason")["initial_revenue"].sum()```
### Calculate call center revenue churn rate by time of day

```python: revenue_churn_rate_by_time = (data.groupby("time_of_day")["initial_revenue"].sum() - data.groupby("time_of_day")["revenue"].sum()) / data.groupby("time_of_day")["initial_revenue"].sum()```
### Calculate call center revenue growth

```python: revenue_growth = (data["revenue"].sum() - data["initial_revenue"].sum()) / data["initial_revenue"].sum()```
### Calculate call center revenue growth by reason

```python: revenue_growth_by_reason = (data.groupby("call_reason")["revenue"].sum() - data.groupby("call_reason")["initial_revenue"].sum()) / data.groupby("call_reason")["initial_revenue"].sum()```
### Calculate call center revenue growth by time of day

```python: revenue_growth_by_time = (data.groupby("time_of_day")["revenue"].sum() - data.groupby("time_of_day")["initial_revenue"].sum()) / data.groupby("time_of_day")["initial_revenue"].sum()```
### Calculate call center revenue per agent

```python: revenue_per_agent = data["revenue"].sum() / data["agent_count"].max()```
### Calculate call center revenue per agent by reason

```python: revenue_per_agent_by_reason = data.groupby("call_reason")["revenue"].sum() / data.groupby("call_reason")["agent_count"].max()```
### Calculate call center revenue per agent by time of day

```python: revenue_per_agent_by_time = data.groupby("time_of_day")["revenue"].sum() / data.groupby("time_of_day")["agent_count"].max()```
