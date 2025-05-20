# Java001
import sys

def get_project_details():
    """Gathers initial project details from the user."""
    details = {}
    print("\n--- Project Setup ---")

    # 1. Understanding the User's Needs - Management Style
    while True:
        methodology = input("First, what project management methodology do you use? (Agile, Kanban, Waterfall, Hybrid, or Other): ").strip().lower()
        if methodology in ['agile', 'kanban', 'waterfall', 'hybrid', 'other']:
            details['methodology'] = methodology.capitalize()
            break
        else:
            print("Invalid methodology. Please choose from Agile, Kanban, Waterfall, Hybrid, or Other.")

    # 2. Gather project details
    print("\nGreat! Now, let's gather some details about your project.")
    details['goals'] = input("What are the main goals of this project? (e.g., Launch new product, Improve efficiency, Reduce costs): ").strip()
    details['stakeholders'] = input("Who are the key stakeholders? (e.g., Management, Customers, Development Team): ").strip()
    details['constraints'] = input("Are there any significant constraints? (e.g., Budget limits, Fixed deadline, Limited resources): ").strip()
    details['timeline'] = input("What is the desired timeline or key dates? (e.g., 6 months, Launch by Q3, Sprint length): ").strip()

    print("\n--- Project Details Captured ---")
    print(f"Methodology: {details['methodology']}")
    print(f"Goals: {details['goals']}")
    print(f"Stakeholders: {details['stakeholders']}")
    print(f"Constraints: {details['constraints']}")
    print(f"Timeline: {details['timeline']}")
    print("------------------------------")

    return details

def handle_planning(details):
    """Simulates generating project planning documents."""
    methodology = details.get('methodology', 'Unknown')
    print(f"\nOkay, let's work on planning using your {methodology} approach.")
    print("Here's what we can generate:")

    print("\n--- Project Planning & Documentation ---")
    print(f"Based on your {methodology} approach:")

    # Tailor based on methodology
    if methodology == 'Agile':
        print("- Generating a Project Charter draft (Scope, Goals, Stakeholders).")
        print("- Outlining potential Epics and User Stories based on your goals.")
        print(f"- Suggesting a Sprint Plan structure (e.g., for a {details.get('timeline', 'typical')} sprint length).")
        print("- Providing a high-level Product Roadmap template.")
    elif methodology == 'Kanban':
        print("- Generating a basic Project Charter draft.")
        print("- Setting up a Kanban board structure (To Do, Doing, Done, etc.).")
        print("- Discussing Work-in-Progress (WIP) limits.")
        print("- Outlining workflow stages.")
    elif methodology == 'Waterfall':
        print("- Generating a comprehensive Project Charter draft.")
        print("- Creating a phased Project Plan structure (Initiation, Planning, Execution, Monitoring, Closure).")
        print("- Outlining key milestones and dependencies based on your timeline.")
        print("- Providing a Gantt chart template idea.")
    else: # Hybrid or Other
        print("- Generating a flexible Project Charter draft.")
        print("- Outlining a hybrid planning structure based on your needs.")
        print("- Discussing key phases or iterations.")

    print("\nAlso providing templates for:")
    print("- Risk Management Plan (Identifying potential issues).")
    print("- Stakeholder Communication Plan (Keeping everyone informed).")

    print("\nWould you like to focus on a specific document now (e.g., fill in the Project Charter)?")

def handle_meetings(details):
    """Simulates generating meeting agendas and templates."""
    methodology = details.get('methodology', 'Unknown')
    print(f"\nOkay, let's prepare for your meetings for this {methodology} project.")

    print("\n--- Meeting Facilitation ---")
    meeting_type = input("Which type of meeting do you need help with? (Stand-up, Sprint Review, Retrospective, Stakeholder Update, Other): ").strip().lower()

    if meeting_type == 'stand-up':
        print("\n--- Daily Stand-up Agenda Template ---")
        print(f"Project: {details.get('goals', 'Your Project Goals')}")
        print("Attendees: Team Members")
        print("Duration: 15 minutes (Timeboxed)")
        print("\nTopics:")
        print("1. What did you do yesterday?")
        print("2. What will you do today?")
        print("3. Are there any impediments blocking your progress?")
        print("\nNotes:")
        print("- Keep answers concise.")
        print("- Discussions should be taken offline after the stand-up.")

    elif meeting_type == 'sprint review' and methodology == 'Agile':
        print("\n--- Sprint Review Agenda Template ---")
        print(f"Project: {details.get('goals', 'Your Project Goals')}")
        print(f"Sprint: [Sprint Number]")
        print("Attendees: Team, Product Owner, Stakeholders")
        print("Duration: 1-2 hours (Timeboxed)")
        print("\nTopics:")
        print("1. Introduction and Sprint Goal Review (Product Owner)")
        print("2. Team presents the work 'Done' during the sprint (Demo)")
        print("3. Discussion and Feedback on the Increment (Stakeholders, Team)")
        print("4. Review of the Product Backlog (What's next?)")
        print("5. Review of the project timeline, budget, potential capabilities for the next release.")
        print("\nNotes:")
        print("- Focus on collaboration and feedback.")
        print("- The goal is to inspect the increment and adapt the backlog.")

    elif meeting_type == 'retrospective' and methodology == 'Agile':
        print("\n--- Sprint Retrospective Agenda Template ---")
        print(f"Project: {details.get('goals', 'Your Project Goals')}")
        print(f"Sprint: [Sprint Number]")
        print("Attendees: Team Members")
        print("Duration: 1 hour (Timeboxed)")
        print("\nTopics:")
        print("1. Set the Stage (Goals of the retro)")
        print("2. Gather Data (What happened? Good/Bad?)")
        print("3. Generate Insights (Why did it happen?)")
        print("4. Decide What to Do (Actionable improvements)")
        print("5. Close the Retrospective (Summarize actions)")
        print("\nNotes:")
        print("- This is a safe space for the team to inspect itself.")
        print("- Focus on continuous improvement.")

    elif meeting_type == 'stakeholder update':
        print("\n--- Stakeholder Update Meeting Agenda Template ---")
        print(f"Project: {details.get('goals', 'Your Project Goals')}")
        print("Attendees: Project Team, Key Stakeholders")
        print("Duration: [Specify Duration]")
        print("\nTopics:")
        print("1. Project Status Update (Overview, Progress against goals)")
        print("2. Key Accomplishments since last meeting")
        print("3. Upcoming activities")
        print("4. Risks or Issues requiring stakeholder input/action")
        print("5. Q&A and Discussion")
        print("\nNotes:")
        print(f"- Tailor the level of detail to your {details.get('stakeholders', 'stakeholders')}.")
        print("- Be prepared to discuss key metrics and progress indicators.")

    else:
        print(f"\nProviding a general meeting agenda template for '{meeting_type}'.")
        print("\n--- General Meeting Agenda Template ---")
        print(f"Meeting Topic: [Specify Topic]")
        print("Date: [Date], Time: [Time]")
        print("Attendees: [List Attendees]")
        print("Duration: [Specify Duration]")
        print("\nTopics:")
        print("1. [Agenda Item 1]")
        print("2. [Agenda Item 2]")
        print("3. [Agenda Item 3]")
        print("...")
        print("\nAction Items:")
        print("- [Action Item, Owner, Due Date]")
        print("\nNotes:")
        print("- Define clear objectives for the meeting.")
        print("- Assign action items with owners and deadlines.")

    print("\nI can also help by suggesting questions to ask or summarizing key points during the meeting.")
    # You could add logic here to ask about specific meeting challenges

def handle_prioritization(details):
    """Simulates guiding the user through prioritization frameworks."""
    print("\nOkay, let's prioritize tasks or projects.")
    print("We can use industry-standard frameworks.")

    print("\n--- Prioritization & Selection Frameworks ---")
    print("Common methods include:")
    print("- Eisenhower Matrix (Urgent vs. Important)")
    print("- MoSCoW (Must-have, Should-have, Could-have, Won't-have)")
    print("- WSJF (Weighted Shortest Job First - for Agile/Flow)")
    print("- RICE (Reach, Impact, Confidence, Effort - for Product Features)")
    print("- Simple Scoring Models")

    framework_choice = input("Which framework would you like to explore or apply? (Eisenhower, MoSCoW, WSJF, RICE, Scoring, Explain): ").strip().lower()

    if framework_choice == 'explain':
        print("\n--- Framework Explanations ---")
        print("Eisenhower Matrix: Helps you decide on tasks by categorizing them based on urgency and importance.")
        print("MoSCoW: A prioritization technique used to reach a clear understanding with stakeholders on the importance they place on the delivery of each requirement.")
        print("WSJF: A prioritization model used to sequence jobs (features, capabilities, epics) to produce the maximum economic benefit.")
        print("RICE: A scoring model used to prioritize product features by scoring them on Reach, Impact, Confidence, and Effort.")
        print("Scoring Models: Assign points based on criteria like value, effort, risk, etc.")
        print("\nWhich framework description was most helpful? Or would you like to try applying one?")

    elif framework_choice in ['eisenhower', 'moscow', 'wsjf', 'rice', 'scoring']:
        print(f"\nOkay, let's apply the {framework_choice.capitalize()} framework.")
        # In a real system, you'd ask for the items to prioritize and then guide them through the steps.
        print(f"To apply {framework_choice.capitalize()}, we need to evaluate your items based on specific criteria.")

        if framework_choice == 'eisenhower':
            print("For each item, tell me if it's Urgent (Yes/No) and Important (Yes/No).")
            print("Output will be categorized as: Do First (Urgent & Important), Schedule (Important, Not Urgent), Delegate (Urgent, Not Important), Don't Do (Not Urgent, Not Important).")
        elif framework_choice == 'moscow':
            print("For each item, classify it as Must-have, Should-have, Could-have, or Won't-have.")
        elif framework_choice == 'wsjf':
             print("For each item, we need values for: User-Business Value, Time Criticality, Risk Reduction/Opportunity Enablement Value, and Job Size.")
             print("WSJF = (Value + Time Criticality + RROE) / Job Size")
        elif framework_choice == 'rice':
            print("For each item, we need values for: Reach (how many people), Impact (how much it helps), Confidence (how sure are you), and Effort (time/resources).")
            print("RICE Score = (Reach * Impact * Confidence) / Effort")
        elif framework_choice == 'scoring':
            print("Let's define the scoring criteria relevant to your project (e.g., Business Value, Technical Effort, Risk). We'll score each item based on these.")

        print(f"\nPlease list the items you want to prioritize, and I will guide you through the evaluation.")
        print("After evaluating, I can generate a prioritization table for you.")

    else:
        print("\nThat's not a standard framework I can guide you through directly, but we can discuss your prioritization criteria.")

def handle_execution(details):
    """Simulates offering workflow and execution support."""
    methodology = details.get('methodology', 'Unknown')
    print(f"\nLet's talk about executing your project using the {methodology} methodology.")

    print("\n--- Workflow & Execution Support ---")

    if methodology == 'Agile':
        print("Guidance for Agile Execution:")
        print("- Best practices for daily stand-ups.")
        print("- Managing the sprint backlog and task workflow.")
        print("- Tips for effective sprint reviews and retrospectives.")
        print("- Ensuring continuous integration and delivery.")
        print("- Handling scope changes within a sprint.")
    elif methodology == 'Kanban':
        print("Guidance for Kanban Execution:")
        print("- Visualizing your workflow on the board.")
        print("- Managing Work-in-Progress (WIP) limits effectively.")
        print("- Measuring flow metrics (Lead Time, Cycle Time).")
        print("- Conducting Kanban ceremonies (replenishment, service delivery review).")
        print("- Identifying and removing bottlenecks.")
    elif methodology == 'Waterfall':
        print("Guidance for Waterfall Execution:")
        print("- Managing phase transitions and sign-offs.")
        print("- Monitoring progress against the baseline plan.")
        print("- Handling change requests formally.")
        print("- Executing according to the detailed project plan.")
        print("- Closing out project phases and the overall project.")
    else: # Hybrid or Other
        print(f"Providing general execution support for your {methodology} approach:")
        print("- Checklists for key phases or activities.")
        print("- Tips for task tracking and status reporting.")
        print("- Strategies for managing dependencies.")

    print("\n--- Ongoing Guidance ---")
    print("I can also help you with:")
    print("- Identifying potential bottlenecks in your workflow.")
    print("- Suggesting process improvements.")
    print("- Providing reminders for recurring tasks or meetings.")
    print("- Offering checklists for key project activities.")

    execution_help = input("What specific execution challenge are you facing right now, or what type of guidance do you need? (e.g., 'bottleneck', 'stand-up tips', 'managing changes'): ").strip().lower()

    if 'bottleneck' in execution_help:
        print("\nLet's analyze your workflow. Where do tasks tend to pile up? What seems to be slowing things down?")
        print("We can look at flow metrics if you have them, or simply discuss where team members are getting stuck.")
    elif 'stand-up tips' in execution_help and methodology == 'Agile':
         print("\nTips for effective daily stand-ups:")
         print("- Start and end on time.")
         print("- Keep it concise (each person ~1-2 mins).")
         print("- Focus on the three questions (Yesterday, Today, Impediments).")
         print("- Resolve deeper discussions outside the meeting.")
    elif 'managing changes' in execution_help:
         print("\nHandling changes depends on your methodology. In Waterfall, changes usually require a formal change control process. In Agile, they are managed via the product backlog and re-prioritization, potentially impacting sprint scope or future sprints.")
         print("Let's discuss your specific change request.")
    else:
        print(f"\nOkay, let's discuss '{execution_help}'. Tell me more about the situation.")


def project_manager_copilot():
    """Main function to run the Project Manager Copilot simulation."""
    print("--- Welcome to Project Manager Copilot ---")
    print("I'm here to help you plan, execute, and document your projects.")

    project_details = get_project_details()

    print("\nHow can I assist you today?")

    while True:
        print("\nPossible tasks:")
        print("1. Planning & Documentation")
        print("2. Meeting Facilitation")
        print("3. Prioritization")
        print("4. Workflow & Execution Support")
        print("5. View Project Details")
        print("6. Exit")

        task_choice = input("Enter the number or name of the task you need help with: ").strip().lower()

        if task_choice in ['1', 'planning', 'planning & documentation']:
            handle_planning(project_details)
        elif task_choice in ['2', 'meeting', 'meeting facilitation']:
            handle_meetings(project_details)
        elif task_choice in ['3', 'prioritization']:
            handle_prioritization(project_details)
        elif task_choice in ['4', 'execution', 'workflow & execution support']:
            handle_execution(project_details)
        elif task_choice in ['5', 'view details', 'project details']:
             print("\n--- Current Project Details ---")
             for key, value in project_details.items():
                 print(f"{key.capitalize()}: {value}")
             print("------------------------------")
        elif task_choice in ['6', 'exit', 'quit']:
            print("\nExiting Project Manager Copilot. Goodbye!")
            sys.exit()
        else:
            print("Sorry, I didn't understand that task. Please choose from the options.")

        input("\nPress Enter to continue or ask for another task...") # Pause for user to read output

if __name__ == "__main__":
    project_manager_copilot()

