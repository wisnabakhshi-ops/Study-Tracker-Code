# Study-Tracker-Code

app.background = 'lightblue'

# Title
Label('Study Tracker', 200, 30, size=24,bold=True)

# Lists
hoursList = []
subjects = []

totalHours = 0


Label('Press keys to add study hours:', 200, 70, size=16)
Label('M = Math | S = Science | E = English', 200, 95, size=16)
Label('H = History | D = Done', 200, 115, size=14)

messageLabel = Label('Press Key to study', 200, 170, size=18,fill='darkBlue')
totalLabel = Label('Total Hours: 0', 200, 210, size=20, bold=True)


mathHours = 0
scienceHours = 0
englishHours = 0
historyHours = 0

mathLabel = Label('Math: 0', 40, 200, size=18)
scienceLabel = Label('Science: 0', 50, 231, size=18)
englishLabel = Label('English: 0', 50, 260, size=18)
historyLabel = Label('History: 0', 50, 290, size= 18)

goalLabel = Label('Goal: 10 Hours',200, 300,size=20,bold=True, fill='green')


def updateTotals():
    global goalReached
    total = sum(hoursList)
    totalLabel.value = 'Total Hours: ' + str(total)
    
    if total >= 10:
        goalLabel.value = 'Goal Reached!'
        goalReached = True
    else:
        goalLabel.value = 'Keep Studying'
        goalReached = False

def onKeyPress(key):
    global mathHours
    global scienceHours
    global englishHours
    global historyHours
    
    if key =='m':
        subjects.append('Math')
        hoursList.append(1)
        mathHours += 1
        mathLabel.value = 'Math: ' + str(mathHours)
        messageLabel.value = 'Added 1 hour to Math'
    
    elif key == 's':
        subjects.append('science')
        hoursList.append(1)
        scienceHours += 1
        scienceLabel.value = 'Science: ' + str(scienceHours)
        messageLabel.value = 'Added 1 hour to Science'
        
    elif key == 'e':
        subjects.append('English')
        hoursList.append(1)
        englishHours += 1
        englishLabel.value = 'English: ' + str(englishHours)
        messageLabel.value = 'Added 1 hour to English'
        
    elif key == 'h':
        subjects.append('History')
        hoursList.append(1)
        historyHours +=1
        historyLabel.value = 'History: ' + str(historyHours)
        messageLabel.value = ' Added 1 hour to History'
        
    elif key == 'd':
        messageLabel.value = 'Study Session Finished'
        
        updateTotals()
        

            
            
        
