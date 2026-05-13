````python
def add_setting(setting, pair):
    user, profile = pair
    
    user, profile = user.lower(), profile.lower()
    
    if user in setting:
        return f"Setting '{user}' already exists! Cannot add a new setting with this name."
    setting[user] = profile
    return f"Setting '{user}' added with value '{profile}' successfully!"

def update_setting(setting, pair):
    additional_settings, date_and_time = pair

    additional_settings = additional_settings.lower()
    date_and_time = date_and_time.lower()
    
    if additional_settings in setting:
        setting[additional_settings] = date_and_time
        return f"Setting '{additional_settings}' updated to '{date_and_time}' successfully!"
    else:
        return f"Setting '{additional_settings}' does not exist! Cannot update a non-existing setting."

def delete_setting(setting, reset_setting):
    
    reset_setting = reset_setting.lower()

    if reset_setting in setting:
        del setting[reset_setting]
        return f"Setting '{reset_setting}' deleted successfully!"
    else:
       return "Setting not found!"

def view_settings(setting):
    
    if not setting:
        return 'No settings available.'
    result = "Current User Settings:\n"
    for key, value in setting.items():  
        result += f"{key.capitalize()}: {value}\n"
    return result
   
test_settings ={
    'theme': 'light'
}

````
