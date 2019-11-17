variable_LED_INDEX = 0
variable_X = 0
variable_Y = 0
list_position_detect = RmList()
def start():
    global variable_LED_INDEX
    global variable_X
    global variable_Y
    global list_position_detect
    led_ctrl.set_top_led(rm_define.armor_top_all, 224, 0, 255, rm_define.effect_always_on)
    chassis_ctrl.enable_stick_overlay()
    vision_ctrl.enable_detection(rm_define.vision_detection_marker)
    variable_LED_INDEX = 5
    while True:
        pass
def vision_recognized_marker_number_two(msg):
    global variable_LED_INDEX
    global variable_X
    global variable_Y
    global list_position_detect
   list_position_detect=RmList(vision_ctrl.get_marker_detection_info())
    variable_X = list_position_detect[3]
    variable_Y = list_position_detect[4]
    if variable_LED_INDEX == 1:
        led_ctrl.set_flash(rm_define.armor_all, 5)
        led_ctrl.set_bottom_led(rm_define.armor_bottom_all, 161, 255, 69, rm_define.effect_flash)
        led_ctrl.set_top_led(rm_define.armor_top_all, 255, 0, 150, rm_define.effect_flash)
        while True:
            chassis_ctrl.disable_stick_overlay()
            media_ctrl.play_sound(rm_define.media_sound_solmization_1C)
            time.sleep(0.4)
            media_ctrl.play_sound(rm_define.media_sound_solmization_1ASharp)
            time.sleep(0.4)
            media_ctrl.play_sound(rm_define.media_sound_solmization_1F)
            time.sleep(0.4)
          media_ctrl.play_sound(rm_define.media_sound_solmization_1G)
           time.sleep(0.4)
            media_ctrl.play_sound(rm_define.media_sound_solmization_1C)
            time.sleep(0.3)
            media_ctrl.play_sound(rm_define.media_sound_solmization_1ASharp)
          time.sleep(0.4)
            media_ctrl.play_sound(rm_define.media_sound_solmization_1F)
            time.sleep(0.4)
            media_ctrl.play_sound(rm_define.media_sound_solmization_1G)
            time.sleep(0.3)
    else:
        if abs(variable_X - 0.5) <= 0.1 and abs(variable_Y - 0.5) <= 0.1:
            gun_ctrl.fire_once()
            led_ctrl.gun_led_on()
            media_ctrl.play_sound(rm_define.media_sound_recognize_success,wait_for_complete_flag=True)
            variable_LED_INDEX = variable_LED_INDEX - 1
            led_ctrl.set_single_led(rm_define.armor_top_all, variable_LED_INDEX, rm_define.effect_always_off)
            led_ctrl.gun_led_off()
            time.sleep(1)        
