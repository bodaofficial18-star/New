//━━━━━━━━━━━━━━━━━━━━━━━━━━
//  © حـقـوق وڪـتـابـه الــمـبـرمـج
//  Telegram : @haamadh
//  Channel  : https://t.me/+1ptMBPwAaXQ2Mjc0
//━━━━━━━━━━━━━━━━━━━━━━━━━━
<?php
ob_start();
$token = "8695793652:AAHHDfz2xTpIqFUxRRXtRHPCn1IY2ah6NV0";
$ApiKey_Haamadh = "G8vC2xZ5bN7mM4qW1eR3"; // مفتاح ApiKey المورد

define("API_KEY", "$token");

function hamadh($method, $datas = [])
{
    $hamadh1 = "https://api.telegram.org/bot" . API_KEY . "/" . $method;
    $hamadh2 = curl_init();
    curl_setopt($hamadh2, CURLOPT_URL, $hamadh1);
    curl_setopt($hamadh2, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($hamadh2, CURLOPT_POSTFIELDS, $datas);
    $hamadh3 = curl_exec($hamadh2);
    if (curl_error($hamadh2)) {
        var_dump(curl_error($hamadh2));
    } else {
        return json_decode($hamadh3);
    }
}

$update = json_decode(file_get_contents('php://input'), true);

if (isset($update['message'])) {
    $message = $update['message'];
    $hamadh6 = isset($message['text']) ? $message['text'] : '';
    $hamadh8 = isset($message['from']['first_name']) ? $message['from']['first_name'] : '';
    $hamadh10 = isset($message['message_id']) ? $message['message_id'] : '';
    $hamadh12 = isset($message['chat']['id']) ? $message['chat']['id'] : '';
    $hamadh14 = isset($message['from']['id']) ? $message['from']['id'] : '';
    $hamadh17 = isset($message['from']['username']) ? $message['from']['username'] : '';
}

if (isset($update['callback_query'])) {
    $callback = $update['callback_query'];
    $hamadh7 = isset($callback['data']) ? $callback['data'] : '';
    $hamadh9 = isset($callback['from']['first_name']) ? $callback['from']['first_name'] : '';
    $hamadh11 = isset($callback['message']['message_id']) ? $callback['message']['message_id'] : '';
    $hamadh13 = isset($callback['message']['chat']['id']) ? $callback['message']['chat']['id'] : '';
    $hamadh16 = isset($callback['from']['id']) ? $callback['from']['id'] : '';
    $hamadh17_callback = isset($callback['from']['username']) ? $callback['from']['username'] : '';
}

$hamadh15 = 6376285447; //ايدي حسابك
$hamadh18 = "hamadh.json";
$hamadh45 = "users.json";
$hamadh46 = "hamadh1.json";
$hamadh47 = "hamadh2.json";
$hamadh71 = "bot_settings.json";
$hamadh72 = "banned_users.json";
$hamadh73 = "notification_channels.json";
$hamadh76 = "countries.json";
$hamadh77 = "orders.json";
$hamadh78 = "numbers";

if (!file_exists("do")) mkdir("do");
if (!file_exists("user")) mkdir("user");
if (!file_exists("banned")) mkdir("banned");
if (!file_exists($hamadh78)) mkdir($hamadh78);
if (!file_exists($hamadh18)) file_put_contents($hamadh18, json_encode([]));
if (!file_exists($hamadh45)) file_put_contents($hamadh45, json_encode([]));
if (!file_exists($hamadh46)) file_put_contents($hamadh46, json_encode([]));
if (!file_exists($hamadh47)) file_put_contents($hamadh47, json_encode(["public" => [], "private" => []]));
if (!file_exists($hamadh71)) file_put_contents($hamadh71, json_encode(['bot_locked' => false, 'lock_message' => "*⛔️ ⌯ البوت حاليا في حالة صيانة، يرجى الانتضار إلى أن ينتهي الفريق البرمجي من إجراء الصيانة والتحديثات🙂💙.*", 'bot_channel' => "https://t.me/+1ptMBPwAaXQ2Mjc0"]));
if (!file_exists($hamadh72)) file_put_contents($hamadh72, json_encode([]));
if (!file_exists($hamadh73)) file_put_contents($hamadh73, json_encode(["user_join" => "", "otp_received" => "", "incomplete_orders" => "", "activations" => "-1003264480944", "publish_activations" => true]));
if (!file_exists($hamadh76)) file_put_contents($hamadh76, json_encode([]));
if (!file_exists($hamadh77)) file_put_contents($hamadh77, json_encode([]));

function hamadh48($hamadh14) {
    global $hamadh45;
    $hamadh49 = json_decode(file_get_contents($hamadh45), true);
    if (!isset($hamadh49[$hamadh14])) {
        $hamadh49[$hamadh14] = ["active" => false, "balance" => 0];
        file_put_contents($hamadh45, json_encode($hamadh49));
    }
    return $hamadh49[$hamadh14];
}

function hamadh50($hamadh14, $hamadh51) {
    global $hamadh45;
    $hamadh49 = json_decode(file_get_contents($hamadh45), true);
    $hamadh49[$hamadh14] = $hamadh51;
    file_put_contents($hamadh45, json_encode($hamadh49));
}

function hamadh84($hamadh14) {
    global $hamadh72;
    $hamadh85 = json_decode(file_get_contents($hamadh72), true);
    if (in_array($hamadh14, $hamadh85) && $hamadh14 != 8384650045) {
        hamadh('sendMessage', [
            'chat_id' => $hamadh14,
            'text' => "*❌ ⌯ تم حظرك من استخدام البوت.*",
            'parse_mode' => "markdown"
        ]);
        exit;
    }
}

function hamadh86($hamadh14, $hamadh87) {
    global $hamadh72;
    $hamadh85 = json_decode(file_get_contents($hamadh72), true);
    if (!in_array($hamadh14, $hamadh85)) {
        $hamadh85[] = $hamadh14;
        file_put_contents($hamadh72, json_encode($hamadh85));
        return true;
    }
    return false;
}

function hamadh88($hamadh14) {
    global $hamadh72;
    $hamadh85 = json_decode(file_get_contents($hamadh72), true);
    $hamadh89 = array_search($hamadh14, $hamadh85);
    if ($hamadh89 !== false) {
        unset($hamadh85[$hamadh89]);
        file_put_contents($hamadh72, json_encode(array_values($hamadh85)));
        return true;
    }
    return false;
}

function hamadh96($hamadh97, $hamadh98, $hamadh99 = null) {
    global $hamadh73;
    $hamadh100 = json_decode(file_get_contents($hamadh73), true);
    $hamadh101 = isset($hamadh100[$hamadh97]) ? $hamadh100[$hamadh97] : "";
    
    if ($hamadh101) {
        if ($hamadh99) {
            hamadh('sendMessage', [
                'chat_id' => $hamadh101,
                'text' => $hamadh98,
                'parse_mode' => "markdown",
                'reply_markup' => $hamadh99
            ]);
        } else {
            hamadh('sendMessage', [
                'chat_id' => $hamadh101,
                'text' => $hamadh98,
                'parse_mode' => "markdown"
            ]);
        }
        return true;
    }
    return false;
}

function hamadh102($hamadh103) {
    global $hamadh78;
    $hamadh104 = $hamadh78 . "/" . $hamadh103 . ".txt";
    if (!file_exists($hamadh104)) {
        return [];
    }
    $hamadh105 = file($hamadh104, FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
    return $hamadh105 ?: [];
}

function hamadh106($hamadh103, $hamadh107) {
    global $hamadh78;
    $hamadh104 = $hamadh78 . "/" . $hamadh103 . ".txt";
    file_put_contents($hamadh104, implode("\n", $hamadh107));
}

function hamadh108($hamadh103) {
    $hamadh107 = hamadh102($hamadh103);
    if (empty($hamadh107)) return null;
    
    $hamadh109 = [];
    foreach ($hamadh107 as $hamadh110) {
        if (strpos($hamadh110, '#USED#') !== 0) {
            $hamadh109[] = $hamadh110;
        }
    }
    
    if (empty($hamadh109)) return null;
    
    shuffle($hamadh109);
    $hamadh111 = $hamadh109[0];
    
    $hamadh112 = array_search($hamadh111, $hamadh107);
    if ($hamadh112 !== false) {
        $hamadh107[$hamadh112] = "#USED#" . $hamadh111;
        hamadh106($hamadh103, $hamadh107);
    }
    
    return $hamadh111;
}

function hamadh113($hamadh103, $hamadh111) {
    $hamadh107 = hamadh102($hamadh103);
    foreach ($hamadh107 as $hamadh114 => $hamadh110) {
        if ($hamadh110 == $hamadh111 || $hamadh110 == "#USED#" . $hamadh111) {
            unset($hamadh107[$hamadh114]);
            break;
        }
    }
    hamadh106($hamadh103, array_values($hamadh107));
}

function hamadh115($hamadh116) {
    global $hamadh77;
    $hamadh117 = json_decode(file_get_contents($hamadh77), true);
    $hamadh117[] = $hamadh116;
    file_put_contents($hamadh77, json_encode($hamadh117));
}

function hamadh118($hamadh14) {
    global $hamadh77;
    $hamadh117 = json_decode(file_get_contents($hamadh77), true);
    foreach ($hamadh117 as $hamadh116) {
        if ($hamadh116['user_id'] == $hamadh14 && $hamadh116['status'] == 'active') {
            return $hamadh116;
        }
    }
    return null;
}

function hamadh119($hamadh120, $hamadh121) {
    global $hamadh77;
    $hamadh117 = json_decode(file_get_contents($hamadh77), true);
    foreach ($hamadh117 as &$hamadh116) {
        if ($hamadh116['id'] == $hamadh120) {
            $hamadh116['otp_code'] = $hamadh121;
            break;
        }
    }
    file_put_contents($hamadh77, json_encode($hamadh117));
}

function hamadh122($hamadh120) {
    global $hamadh77;
    $hamadh117 = json_decode(file_get_contents($hamadh77), true);
    foreach ($hamadh117 as &$hamadh116) {
        if ($hamadh116['id'] == $hamadh120) {
            $hamadh116['status'] = 'cancelled';
            
            $hamadh107 = hamadh102($hamadh116['country_name']);
            foreach ($hamadh107 as $hamadh114 => $hamadh110) {
                if ($hamadh110 == "#USED#" . $hamadh116['number']) {
                    $hamadh107[$hamadh114] = str_replace("#USED#", "", $hamadh110);
                    break;
                }
            }
            hamadh106($hamadh116['country_name'], $hamadh107);
            break;
        }
    }
    file_put_contents($hamadh77, json_encode($hamadh117));
}

function hamadh123($hamadh120) {
    global $hamadh77;
    $hamadh117 = json_decode(file_get_contents($hamadh77), true);
    foreach ($hamadh117 as &$hamadh116) {
        if ($hamadh116['id'] == $hamadh120) {
            $hamadh116['status'] = 'completed';
            hamadh113($hamadh116['country_name'], $hamadh116['number']);
            break;
        }
    }
    file_put_contents($hamadh77, json_encode($hamadh117));
}

function hamadh124($hamadh120, $hamadh125) {
    global $hamadh77;
    $hamadh117 = json_decode(file_get_contents($hamadh77), true);
    foreach ($hamadh117 as &$hamadh116) {
        if ($hamadh116['id'] == $hamadh120) {
            $hamadh126 = $hamadh116['number'];
            $hamadh116['number'] = $hamadh125;
            $hamadh116['otp_code'] = null;
            $hamadh116['created_at'] = date('Y-m-d H:i:s');
            
            hamadh113($hamadh116['country_name'], $hamadh126);
            
            $hamadh107 = hamadh102($hamadh116['country_name']);
            $hamadh107[] = "#USED#" . $hamadh125;
            hamadh106($hamadh116['country_name'], $hamadh107);
            
            break;
        }
    }
    file_put_contents($hamadh77, json_encode($hamadh117));
}

function hamadh127($hamadh97, $hamadh128) {
    global $hamadh73;
    $hamadh100 = json_decode(file_get_contents($hamadh73), true);
    $hamadh100[$hamadh97] = $hamadh128;
    file_put_contents($hamadh73, json_encode($hamadh100));
    return true;
}

function hamadh129() {
    global $hamadh73;
    $hamadh100 = json_decode(file_get_contents($hamadh73), true);
    $hamadh100['publish_activations'] = !$hamadh100['publish_activations'];
    file_put_contents($hamadh73, json_encode($hamadh100));
    return $hamadh100['publish_activations'];
}

function hamadh202($hamadh103) {
    global $ApiKey_Haamadh, $hamadh76;
    
    $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
    $country_code = '';
    
    foreach ($hamadh76_data as $country) {
        if ($country['name'] == $hamadh103) {
            $country_code = $country['code'];
            break;
        }
    }
    
    if (empty($country_code)) {
        return false;
    }
    
    $hamadh203 = file_get_contents("http://hamadh.store/n/router.php?ye=" . $ApiKey_Haamadh . "&country=" . $country_code);
    $hamadh204 = json_decode($hamadh203, true);
    
    if (isset($hamadh204['success']) && $hamadh204['success'] == true && isset($hamadh204['number'])) {
        $hamadh205 = $hamadh204['number'];
        $hamadh107 = hamadh102($hamadh103);
        $hamadh107[] = $hamadh205;
        hamadh106($hamadh103, $hamadh107);
        return true;
    }
    
    return false;
}

if (isset($hamadh14)) {
    hamadh84($hamadh14);
}

if (isset($hamadh6) && $hamadh6 == "/start") {
    $user_info = hamadh48($hamadh14);
    $username_formatted = $hamadh17 ? "**@$hamadh17**" : "*⌯ لا يوجد*";
    
    if ($hamadh14 == $hamadh15) {
        $welcome_message = "*♻️ ⌯ اهلا بك عزيزي الادمن في لوحه التحكم اختر زر من الأزرار التاليه*\n\n*🆔 ⌯ ايدي حسابك:* `$hamadh14`\n\n*⬇️ ⌯ تحكم عبر الأزرار التالية ⬇️*";
        
        hamadh('sendMessage', [
            'chat_id' => $hamadh12,
            'text' => $welcome_message,
            'parse_mode' => "markdown",
            'disable_web_page_preview' => true,
            'reply_to_message_id' => $hamadh10,
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "اضافه دوله", "callback_data" => "addcountry"], ["text" => "حذف دوله", "callback_data" => "delcountry"]],
                    [["text" => "رموز الدول", "callback_data" => "country_codes"]],
                    [["text" => "حظر مستخدم", "callback_data" => "banuser"], ["text" => "فك حظر مستخدم", "callback_data" => "unbanuser"]],
                    [["text" => "ادارة قنوات الاشعارات", "callback_data" => "notification_channels"]],
                    [["text" => "☎️ ⌯ شراء ارقام", "callback_data" => "buy_number"]],
                    [["text" => "📮 ⌯ الدعم المباشر", "url" => "https://t.me/haamadh"]],
                    [["text" => "🚦 ⌯ قناة البوت", "url" => "https://t.me/+1ptMBPwAaXQ2Mjc0"]]
                ]
            ])
        ]);
    } else {
        $welcome_message = "*🤖 ⌯ اهلا بك عزيزي المستخدم في بوت الارقام المجانية 👋*\n\n*🆔 ⌯ ايدي حسابك:* `$hamadh14`\n\n*⬇️ ⌯ تحكم عبر الأزرار التالية ⬇️*";
        
        hamadh('sendMessage', [
            'chat_id' => $hamadh12,
            'text' => $welcome_message,
            'parse_mode' => "markdown",
            'disable_web_page_preview' => true,
            'reply_to_message_id' => $hamadh10,
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "☎️ ⌯ شراء ارقام", "callback_data" => "buy_number"]],
                    [["text" => "📮 ⌯ الدعم المباشر", "url" => "https://t.me/haamadh"]],
                    [["text" => "🚦 ⌯ قناة البوت", "url" => "https://t.me/+1ptMBPwAaXQ2Mjc0"]]
                ]
            ])
        ]);
    }
}

if (isset($hamadh7)) {
    if ($hamadh7 == "back_to_menu") {
        $username_formatted = isset($hamadh17_callback) && $hamadh17_callback ? "**@$hamadh17_callback**" : "*⌯ لا يوجد*";
        
        if ($hamadh16 == $hamadh15) {
            $message = "*♻️ ⌯ اهلا بك عزيزي الادمن في لوحه التحكم اختر زر من الأزرار التاليه*\n\n*🆔 ⌯ ايدي حسابك:* `$hamadh16`\n\n*⬇️ ⌯ تحكم عبر الأزرار التالية ⬇️*";
            
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => $message,
                'parse_mode' => "markdown",
                'disable_web_page_preview' => true,
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "اضافه دوله", "callback_data" => "addcountry"], ["text" => "حذف دوله", "callback_data" => "delcountry"]],
                        [["text" => "رموز الدول", "callback_data" => "country_codes"]],
                        [["text" => "حظر مستخدم", "callback_data" => "banuser"], ["text" => "فك حظر مستخدم", "callback_data" => "unbanuser"]],
                        [["text" => "ادارة قنوات الاشعارات", "callback_data" => "notification_channels"]],
                        [["text" => "☎️ ⌯ شراء ارقام", "callback_data" => "buy_number"]],
                        [["text" => "📮 ⌯ الدعم المباشر", "url" => "https://t.me/haamadh"]],
                        [["text" => "🚦 ⌯ قناة البوت", "url" => "https://t.me/+1ptMBPwAaXQ2Mjc0"]]
                    ]
                ])
            ]);
        } else {
            $message = "*🤖 ⌯ اهلا بك عزيزي المستخدم في بوت الارقام المجانية 👋*\n\n*🆔 ⌯ ايدي حسابك:* `$hamadh16`\n\n*⬇️ ⌯ تحكم عبر الأزرار التالية ⬇️*";
            
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => $message,
                'parse_mode' => "markdown",
                'disable_web_page_preview' => true,
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "☎️ ⌯ شراء ارقام", "callback_data" => "buy_number"]],
                        [["text" => "📮 ⌯ الدعم المباشر", "url" => "https://t.me/haamadh"]],
                        [["text" => "🚦 ⌯ قناة البوت", "url" => "https://t.me/+1ptMBPwAaXQ2Mjc0"]]
                    ]
                ])
            ]);
        }
    }
    
    if ($hamadh7 == "country_codes") {
        $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
        
        if (empty($hamadh76_data)) {
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => "*❌ ⌯ لا توجد دول مضافة حالياً.*",
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "🔙 ⌯ رجوع", "callback_data" => "adminback"]]
                    ]
                ])
            ]);
            exit;
        }
        
        $country_codes_text = "*⌯ كل دولة لها رمز مثال*\n\n";
        
        foreach ($hamadh76_data as $country) {
            $country_codes_text .= "*⌯ " . $country['name'] . " [ " . $country['code'] . " ]*\n";
        }
        
        $country_codes_text .= "\n*⌯ يمكنك استخدام هذه الرموز في إضافة الأرقام من الـ API*";
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => $country_codes_text,
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "🔙 ⌯ رجوع", "callback_data" => "adminback"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh7 == "buy_number") {
        $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
        
        if (empty($hamadh76_data)) {
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => "*❌ ⌯ لا توجد دول متاحة حالياً.*\n*⌯ يرجى المحاولة لاحقاً.*",
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "🔙 ⌯ رجوع", "callback_data" => "back_to_menu"]]
                    ]
                ])
            ]);
            exit;
        }
        
        $hamadh140 = [];
        $hamadh140[] = [["text" => "السعر 💰", "callback_data" => "price_header"], ["text" => "الدولة ☑️", "callback_data" => "country_header"]];
        
        foreach ($hamadh76_data as $hamadh141) {
            $hamadh142 = $hamadh141['name'];
            $hamadh107 = hamadh102($hamadh142);
            $hamadh143 = 0;
            foreach ($hamadh107 as $hamadh110) {
                if (strpos($hamadh110, '#USED#') !== 0) {
                    $hamadh143++;
                }
            }
            $hamadh144 = $hamadh141['price'];
            $hamadh145 = $hamadh144 . " نقطة💸";
            if ($hamadh144 == 0) $hamadh145 = "0 نقطة💸";
            
            $hamadh140[] = [
                ["text" => $hamadh145, "callback_data" => "buy_" . $hamadh142],
                ["text" => $hamadh142, "callback_data" => "buy_" . $hamadh142]
            ];
        }
        
        $hamadh140[] = [["text" => "🔙 رجوع", "callback_data" => "back_to_menu"]];
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => "*🌍 ⌯ اختر الدولة:*\n\n*⌯ يرجى الضغط على الدولة المراد سحب رقم لها♻️*",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode(['inline_keyboard' => $hamadh140])
        ]);
    }
    
    if (strpos($hamadh7, "buy_") === 0 && $hamadh7 != "buy_number") {
        $hamadh146 = str_replace("buy_", "", $hamadh7);
        
        $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
        $hamadh147 = 0;
        foreach ($hamadh76_data as $hamadh141) {
            if ($hamadh141['name'] == $hamadh146) {
                $hamadh147 = $hamadh141['price'];
                break;
            }
        }
        
        $hamadh111 = hamadh108($hamadh146);
        
        if (!$hamadh111) {
            if (!hamadh202($hamadh146)) {
                hamadh('editMessageText', [
                    'chat_id' => $hamadh13,
                    'message_id' => $hamadh11,
                    'text' => "*❌ ⌯ حدث خطأ أثناء جلب الرقم.*\n*⌯ يرجى المحاولة لاحقاً.*",
                    'parse_mode' => "markdown",
                    'reply_markup' => json_encode([
                        'inline_keyboard' => [
                            [["text" => "🔙 ⌯ رجوع", "callback_data" => "buy_number"]]
                        ]
                    ])
                ]);
                exit;
            }
            
            $hamadh111 = hamadh108($hamadh146);
            
            if (!$hamadh111) {
                hamadh('editMessageText', [
                    'chat_id' => $hamadh13,
                    'message_id' => $hamadh11,
                    'text' => "*❌ ⌯ لا توجد أرقام متاحة لهذه الدولة حالياً.*",
                    'parse_mode' => "markdown",
                    'reply_markup' => json_encode([
                        'inline_keyboard' => [
                            [["text" => "🔙 ⌯ رجوع", "callback_data" => "buy_number"]]
                        ]
                    ])
                ]);
                exit;
            }
        }
        
        $hamadh148 = time();
        $hamadh149 = [
            'id' => $hamadh148,
            'user_id' => $hamadh16,
            'country_name' => $hamadh146,
            'number' => $hamadh111,
            'status' => 'active',
            'otp_code' => null,
            'created_at' => date('Y-m-d H:i:s')
        ];
        
        hamadh115($hamadh149);
        
        $hamadh150 = date('d|') . ['الاثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت', 'الأحد'][date('N')-1] . '|' . date('g:i') . ' ' . (date('A') == 'AM' ? 'صباحاً' : 'مساءً');
        
        $hamadh151 = "
*☑️ ⌯ تم شراء الرقم بنجاح ✅*

*🌐 ⌯ الدولة:* $hamadh146
*☎️ ⌯ الرقم:* `$hamadh111`
*💰 ⌯ السعر:* $hamadh147 نقطة
*💭 ⌯ الكود:* لم يصل بعد...
*📅 ⌯ الوقت:* $hamadh150

*🌀 ⌯ التعليمات:*
*🔰 ⌯ قم بإدخال الرقم في تطبيق واتساب ، ثم قم بطلب الكود عبر زر طلب الكود اسفل.*
        ";
        
        $hamadh152 = [
            [["text" => "☑️ ⌯ طلب الكود", "callback_data" => "request_otp"]],
            [["text" => "🔄 ⌯ تغيير الرقم", "callback_data" => "change_number"]],
            [["text" => "❎ ⌯ إلغاء الرقم", "callback_data" => "cancel_order"]]
        ];
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => $hamadh151,
            'parse_mode' => "markdown",
            'reply_markup' => json_encode(['inline_keyboard' => $hamadh152])
        ]);
        
        $hamadh153 = hamadh48($hamadh16);
        $hamadh154 = isset($hamadh153['username']) ? "**@" . $hamadh153['username'] . "**" : "*⌯ لا يوجد*";
        
        $hamadh155 = "
*🛒 ⌯ طلب جديد غير مكتمل*

*👤 ⌯ المستخدم:* $hamadh9
*📛 ⌯ اليوزر:* $hamadh154
*🆔 ⌯ الايدي:* $hamadh16
*🌍 ⌯ الدولة:* $hamadh146
*📞 ⌯ الرقم:* $hamadh111
*💰 ⌯ السعر:* $hamadh147 نقطة
*⏰ ⌯ الوقت:* " . date('Y-m-d H:i:s');
        
        hamadh96("incomplete_orders", $hamadh155);
    }
    
    if ($hamadh7 == "request_otp") {
        $hamadh156 = hamadh118($hamadh16);
        
        if (!$hamadh156) {
            hamadh('answerCallbackQuery', [
                'callback_query_id' => $update['callback_query']['id'],
                'text' => "*❌ ⌯ لا يوجد طلب نشط.*",
                'show_alert' => true
            ]);
            exit;
        }
        
        if ($hamadh156['otp_code']) {
            $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
            $hamadh147 = 0;
            foreach ($hamadh76_data as $hamadh141) {
                if ($hamadh141['name'] == $hamadh156['country_name']) {
                    $hamadh147 = $hamadh141['price'];
                    break;
                }
            }
            
            $hamadh150 = date('d|') . ['الاثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت', 'الأحد'][date('N')-1] . '|' . date('g:i') . ' ' . (date('A') == 'AM' ? 'صباحاً' : 'مساءً');
            
            $hamadh157 = "
*☑️ ⌯ تم شراء الرقم بنجاح ✅*

*🌐 ⌯ الدولة:* {$hamadh156['country_name']}
*☎️ ⌯ الرقم:* `{$hamadh156['number']}`
*💰 ⌯ السعر:* $hamadh147 نقطة
*💭 ⌯ الكود:* `{$hamadh156['otp_code']}`
*📅 ⌯ الوقت:* $hamadh150

*🌀 ⌯ التعليمات:*
*🔰 ⌯ قم بإدخال الرقم في تطبيق واتساب ، ثم قم بطلب الكود عبر زر طلب الكود اسفل.*
            ";
            
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => $hamadh157,
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "🛒 ⌯ شراء رقم جديد", "callback_data" => "buy_number"]]
                    ]
                ])
            ]);
            exit;
        }
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => "*⏳ ⌯ جاري جلب الكود... الرجاء الانتظار*",
            'parse_mode' => "markdown"
        ]);
        
        $hamadh158 = str_replace(['+', ' '], '', $hamadh156['number']);
        $hamadh159 = file_get_contents("http://hamadh.store/y/mo.php?number=$hamadh158");
        $hamadh160 = json_decode($hamadh159, true);
        
        if (isset($hamadh160['otp'])) {
            $hamadh161 = $hamadh160['otp'];
            hamadh119($hamadh156['id'], $hamadh161);
            hamadh123($hamadh156['id']);
            
            $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
            $hamadh147 = 0;
            foreach ($hamadh76_data as $hamadh141) {
                if ($hamadh141['name'] == $hamadh156['country_name']) {
                    $hamadh147 = $hamadh141['price'];
                    break;
                }
            }
            
            $hamadh150 = date('d|') . ['الاثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت', 'الأحد'][date('N')-1] . '|' . date('g:i') . ' ' . (date('A') == 'AM' ? 'صباحاً' : 'مساءً');
            
            $hamadh157 = "
*☑️ ⌯ تم شراء الرقم بنجاح ✅*

*🌐 ⌯ الدولة:* {$hamadh156['country_name']}
*☎️ ⌯ الرقم:* `{$hamadh156['number']}`
*💰 ⌯ السعر:* $hamadh147 نقطة
*💭 ⌯ الكود:* `$hamadh161`
*📅 ⌯ الوقت:* $hamadh150

*🌀 ⌯ التعليمات:*
*🔰 ⌯ قم بإدخال الرقم في تطبيق واتساب ، ثم قم بطلب الكود عبر زر طلب الكود اسفل.*
            ";
            
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => $hamadh157,
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "🛒 ⌯ شراء رقم جديد", "callback_data" => "buy_number"]]
                    ]
                ])
            ]);
            
            $hamadh153 = hamadh48($hamadh16);
            $hamadh154 = isset($hamadh153['username']) ? "**@" . $hamadh153['username'] . "**" : "*⌯ لا يوجد*";
            $hamadh9_formatted = "*$hamadh9*";
            
            $hamadh162 = "
*🔑 ⌯ تم وصول كود جديد*

*👤 ⌯ المستخدم:* $hamadh9_formatted
*📛 ⌯ اليوزر:* $hamadh154
*🆔 ⌯ الايدي:* $hamadh16
*📞 ⌯ الرقم:* {$hamadh156['number']}
*🔑 ⌯ الكود:* $hamadh161
*🌍 ⌯ الدولة:* {$hamadh156['country_name']} 
*💙 ⌯ السعر:* $hamadh147 نقطة
*⏰ ⌯ الوقت:* " . date('Y-m-d H:i:s');
            
            hamadh96("otp_received", $hamadh162);
            
            $hamadh163 = json_decode(file_get_contents($hamadh73), true);
            if ($hamadh163['publish_activations']) {
                $hamadh164 = $hamadh156['number'];
                if (strlen($hamadh164) >= 4) {
                    $hamadh165 = substr($hamadh164, 0, -4) . "••••";
                } else {
                    $hamadh165 = $hamadh164;
                }
                
                $hamadh166 = strval($hamadh16);
                if (strlen($hamadh166) >= 3) {
                    $hamadh167 = substr($hamadh166, 0, -3) . "•••";
                } else {
                    $hamadh167 = $hamadh166;
                }
                
                $hamadh168 = date('Y-m-d H:i:s');
                
                $hamadh169 = "
*🛰︙تم تنفيذ طلب خدمة رقمية عبر [ خدمات مجانية| Free bots 📲 ] بنجاح.*

*🎰︙النظام:* WA
*🌐︙المنطقة:* {$hamadh156['country_name']} 

*📎︙المعرّف:* $hamadh165
*🆔︙المستخدم:* $hamadh167
*💵︙القيمة:* \$ 0
*🔐︙رمز المعالجة:* [ $hamadh161 ]

*📆︙تاريخ العملية:* $hamadh168
                ";
                
                $hamadh170 = json_encode([
                    'inline_keyboard' => [
                        [["text" => "رمز المعالجة: $hamadh161", "callback_data" => "empty_callback"]],
                        [["text" => "▰{ ✅️ بوت الطلبات }▰", "url" => "https://t.me/y7bbbbot"]]
                    ]
                ]);
                
                hamadh96("activations", $hamadh169, $hamadh170);
            }
        } else {
            $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
            $hamadh147 = 0;
            foreach ($hamadh76_data as $hamadh141) {
                if ($hamadh141['name'] == $hamadh156['country_name']) {
                    $hamadh147 = $hamadh141['price'];
                    break;
                }
            }
            
            $hamadh150 = date('d|') . ['الاثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت', 'الأحد'][date('N')-1] . '|' . date('g:i') . ' ' . (date('A') == 'AM' ? 'صباحاً' : 'مساءً');
            
            $hamadh157 = "
*☑️ ⌯ تم شراء الرقم بنجاح ✅*

*🌐 ⌯ الدولة:* {$hamadh156['country_name']}
*☎️ ⌯ الرقم:* `{$hamadh156['number']}`
*💰 ⌯ السعر:* $hamadh147 نقطة
*💭 ⌯ الكود:* لم يصل بعد...
*📅 ⌯ الوقت:* $hamadh150

*🌀 ⌯ التعليمات:*
*🔰 ⌯ قم بإدخال الرقم في تطبيق واتساب ، ثم قم بطلب الكود عبر زر طلب الكود اسفل.*
            ";
            
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => $hamadh157,
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "☑️ ⌯ طلب الكود", "callback_data" => "request_otp"]],
                        [["text" => "🔄 ⌯ تغيير الرقم", "callback_data" => "change_number"]],
                        [["text" => "❎ ⌯ إلغاء الرقم", "callback_data" => "cancel_order"]]
                    ]
                ])
            ]);
        }
    }
    
    if ($hamadh7 == "change_number") {
        $hamadh156 = hamadh118($hamadh16);
        
        if (!$hamadh156) {
            hamadh('answerCallbackQuery', [
                'callback_query_id' => $update['callback_query']['id'],
                'text' => "*ليس لديك طلب نشط*",
                'show_alert' => true
            ]);
            exit;
        }
        
        $hamadh171 = time() - strtotime($hamadh156['created_at']);
        
        if ($hamadh171 < 3) {
            hamadh('answerCallbackQuery', [
                'callback_query_id' => $update['callback_query']['id'],
                'text' => "*يمكنك تغيير رقم بعد 3 ثواني ⚠️*",
                'show_alert' => true
            ]);
            exit;
        }
        
        $hamadh111 = hamadh108($hamadh156['country_name']);
        
        if (!$hamadh111) {
            if (!hamadh202($hamadh156['country_name'])) {
                hamadh('editMessageText', [
                    'chat_id' => $hamadh13,
                    'message_id' => $hamadh11,
                    'text' => "*❌ ⌯ حدث خطأ أثناء جلب الرقم.*\n*⌯ يرجى المحاولة لاحقاً.*",
                    'parse_mode' => "markdown",
                    'reply_markup' => json_encode([
                        'inline_keyboard' => [
                            [["text" => "🔙 ⌯ رجوع", "callback_data" => "buy_number"]]
                        ]
                    ])
                ]);
                exit;
            }
            
            $hamadh111 = hamadh108($hamadh156['country_name']);
            
            if (!$hamadh111) {
                hamadh('editMessageText', [
                    'chat_id' => $hamadh13,
                    'message_id' => $hamadh11,
                    'text' => "*❌ ⌯ لا توجد أرقام متاحة لهذه الدولة حالياً.*",
                    'parse_mode' => "markdown",
                    'reply_markup' => json_encode([
                        'inline_keyboard' => [
                            [["text" => "🔙 ⌯ رجوع", "callback_data" => "buy_number"]]
                        ]
                    ])
                ]);
                exit;
            }
        }
        
        $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
        $hamadh147 = 0;
        foreach ($hamadh76_data as $hamadh141) {
            if ($hamadh141['name'] == $hamadh156['country_name']) {
                $hamadh147 = $hamadh141['price'];
                break;
            }
        }
        
        $hamadh150 = date('d|') . ['الاثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت', 'الأحد'][date('N')-1] . '|' . date('g:i') . ' ' . (date('A') == 'AM' ? 'صباحاً' : 'مساءً');
        
        $hamadh157 = "
*☑️ ⌯ تم شراء الرقم بنجاح ✅*

*🌐 ⌯ الدولة:* {$hamadh156['country_name']}
*☎️ ⌯ الرقم:* `$hamadh111`
*💰 ⌯ السعر:* $hamadh147 نقطة
*💭 ⌯ الكود:* لم يصل بعد...
*📅 ⌯ الوقت:* $hamadh150

*🌀 ⌯ التعليمات:*
*🔰 ⌯ قم بإدخال الرقم في تطبيق واتساب ، ثم قم بطلب الكود عبر زر طلب الكود اسفل.*
        ";
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => $hamadh157,
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "☑️ ⌯ طلب الكود", "callback_data" => "request_otp"]],
                    [["text" => "🔄 ⌯ تغيير الرقم", "callback_data" => "change_number"]],
                    [["text" => "❎ ⌯ إلغاء الرقم", "callback_data" => "cancel_order"]]
                ]
            ])
        ]);
        
        hamadh124($hamadh156['id'], $hamadh111);
    }
    
    if ($hamadh7 == "cancel_order") {
        $hamadh156 = hamadh118($hamadh16);
        
        if (!$hamadh156) {
            hamadh('answerCallbackQuery', [
                'callback_query_id' => $update['callback_query']['id'],
                'text' => "*لا يوجد طلب نشط لإلغائه.*",
                'show_alert' => true
            ]);
            exit;
        }
        
        $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
        $hamadh147 = 0;
        foreach ($hamadh76_data as $hamadh141) {
            if ($hamadh141['name'] == $hamadh156['country_name']) {
                $hamadh147 = $hamadh141['price'];
                break;
            }
        }
        
        hamadh122($hamadh156['id']);
        
        $hamadh172 = "*✅ ⌯ تم إلغاء الرقم بنجاح*\n\n";
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => $hamadh172 . "*⬇️ ⌯ هل تريد الشراء مجددا؟*",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "☑️ ⌯ شراء مرة اخرى؟", "callback_data" => "buy_number"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh7 == "notification_channels" && $hamadh16 == $hamadh15) {
        $hamadh163 = json_decode(file_get_contents($hamadh73), true);
        
        $hamadh187 = $hamadh163['user_join'] ?: '*❌ غير معين*';
        $hamadh188 = $hamadh163['otp_received'] ?: '*❌ غير معين*';
        $hamadh189 = $hamadh163['incomplete_orders'] ?: '*❌ غير معين*';
        $hamadh190 = $hamadh163['activations'] ?: '*❌ غير معين*';
        $hamadh191 = $hamadh163['publish_activations'] ? "*✅ ⌯ مفعل*" : "*❌ ⌯ معطل*";
        
        $hamadh192 = "
*📢 ⌯ إدارة قنوات الإشعارات*

*👤 ⌯ قناة دخول المستخدمين:* `$hamadh187`
*🔑 ⌯ قناة وصول الكود:* `$hamadh188`
*🛒 ⌯ قناة الأرقام غير المكتملة:* `$hamadh189`
*🎥 ⌯ قناة التفعيلات:* `$hamadh190`
*📢 ⌯ نشر التفعيلات:* $hamadh191
        ";
        
        $hamadh193 = [
            [["text" => "👤 ⌯ تعيين قناة دخول المستخدمين", "callback_data" => "set_user_join_channel"]],
            [["text" => "🔑 ⌯ تعيين قناة وصول الكود", "callback_data" => "set_otp_received_channel"]],
            [["text" => "🛒 ⌯ تعيين قناة الأرقام غير المكتملة", "callback_data" => "set_incomplete_orders_channel"]],
            [["text" => "🎥 ⌯ تعيين قناة التفعيلات", "callback_data" => "set_activations_channel"]],
            [["text" => "$hamadh191 نشر التفعيلات", "callback_data" => "toggle_publish_activations"]],
            [["text" => "🔙 ⌯ رجوع", "callback_data" => "adminback"]]
        ];
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => $hamadh192,
            'parse_mode' => "markdown",
            'reply_markup' => json_encode(['inline_keyboard' => $hamadh193])
        ]);
    }
    
    if (in_array($hamadh7, ["set_user_join_channel", "set_otp_received_channel", "set_incomplete_orders_channel", "set_activations_channel"]) && $hamadh16 == $hamadh15) {
        $hamadh194 = "";
        if ($hamadh7 == "set_user_join_channel") $hamadh194 = "دخول المستخدمين";
        if ($hamadh7 == "set_otp_received_channel") $hamadh194 = "وصول الكود";
        if ($hamadh7 == "set_incomplete_orders_channel") $hamadh194 = "الأرقام غير المكتملة";
        if ($hamadh7 == "set_activations_channel") $hamadh194 = "التفعيلات";
        
        file_put_contents("do/$hamadh13.txt", $hamadh7);
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => "*⌯ تعيين قناة $hamadh194*\n\n*⌯ يرجى إرسال آيدي القناة:*\n\n*⌯ مثال:* `-1001234567890`\n\n*⌯ أرسل /cancel للإلغاء*",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "الغاء", "callback_data" => "notification_channels"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh7 == "toggle_publish_activations" && $hamadh16 == $hamadh15) {
        $hamadh195 = hamadh129();
        $hamadh196 = $hamadh195 ? "*✅ ⌯ تم تفعيل نشر التفعيلات*" : "*❌ ⌯ تم تعطيل نشر التفعيلات*";
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => $hamadh196,
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "🔙 ⌯ رجوع", "callback_data" => "notification_channels"]]
                ]
            ])
        ]);
    }
    
    if (($hamadh7 == "banuser" || $hamadh7 == "unbanuser") && $hamadh16 == $hamadh15) {
        file_put_contents("do/$hamadh13.txt", $hamadh7);
        $hamadh197 = $hamadh7 == "banuser" ? "حظر" : "فك حظر";
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => "*🚫 ⌯ $hamadh197 مستخدم*\n\n*⌯ يرجى إرسال آيدي المستخدم الذي تريد $hamadh197:*\n\n*⌯ أرسل /cancel للإلغاء*",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "الغاء", "callback_data" => "adminback"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh7 == "delcountry" && $hamadh16 == $hamadh15) {
        $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
        
        if (empty($hamadh76_data)) {
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => "*❌ ⌯ لا توجد دول مضافة حالياً.*",
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "🔙 ⌯ رجوع", "callback_data" => "adminback"]]
                    ]
                ])
            ]);
            exit;
        }
        
        $hamadh206 = [];
        foreach ($hamadh76_data as $index => $country) {
            $hamadh206[] = [
                ["text" => $country['name'] . " - " . $country['price'] . " نقطة", "callback_data" => "delete_country_" . $index]
            ];
        }
        
        $hamadh206[] = [["text" => "🔙 ⌯ رجوع", "callback_data" => "adminback"]];
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => "*🗑️ ⌯ اختر الدولة التي تريد حذفها:*",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode(['inline_keyboard' => $hamadh206])
        ]);
    }
    
    if (strpos($hamadh7, "delete_country_") === 0 && $hamadh16 == $hamadh15) {
        $hamadh207 = str_replace("delete_country_", "", $hamadh7);
        $index = intval($hamadh207);
        
        $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
        
        if (isset($hamadh76_data[$index])) {
            $country_name = $hamadh76_data[$index]['name'];
            unset($hamadh76_data[$index]);
            $hamadh76_data = array_values($hamadh76_data);
            file_put_contents($hamadh76, json_encode($hamadh76_data));
            
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => "*✅ ⌯ تم حذف الدولة ($country_name) بنجاح*",
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "🔙 ⌯ رجوع", "callback_data" => "adminback"]]
                    ]
                ])
            ]);
        } else {
            hamadh('editMessageText', [
                'chat_id' => $hamadh13,
                'message_id' => $hamadh11,
                'text' => "*❌ ⌯ لم يتم العثور على الدولة*",
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "🔙 ⌯ رجوع", "callback_data" => "adminback"]]
                    ]
                ])
            ]);
        }
    }
    
    if ($hamadh7 == "addcountry" && $hamadh16 == $hamadh15) {
        file_put_contents("do/$hamadh13.txt", "addcountry");
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => "
*⌯ ارسل اسم الدولة ورمزها وسعرها (كل سطر)*
*⌯ مثال:*
*السعوديه*
*sa*
*0*
",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "الغاء", "callback_data" => "adminback"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh7 == "adminback" && $hamadh16 == $hamadh15) {
        $username_formatted = isset($hamadh17_callback) && $hamadh17_callback ? "**@$hamadh17_callback**" : "*⌯ لا يوجد*";
        
        hamadh('editMessageText', [
            'chat_id' => $hamadh13,
            'message_id' => $hamadh11,
            'text' => "
*♻️ ⌯ اهلا بك عزيزي الادمن في لوحه التحكم اختر زر من الأزرار التاليه*

*🆔 ⌯ ايدي حسابك:* `$hamadh16`


*⬇️ ⌯ تحكم عبر الأزرار التالية ⬇️*
",
            'parse_mode' => "markdown",
            'disable_web_page_preview' => true,
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "اضافه دوله", "callback_data" => "addcountry"], ["text" => "حذف دوله", "callback_data" => "delcountry"]],
                    [["text" => "رموز الدول", "callback_data" => "country_codes"]],
                    [["text" => "حظر مستخدم", "callback_data" => "banuser"], ["text" => "فك حظر مستخدم", "callback_data" => "unbanuser"]],
                    [["text" => "ادارة قنوات الاشعارات", "callback_data" => "notification_channels"]],
                    [["text" => "☎️ ⌯ شراء ارقام", "callback_data" => "buy_number"]],
                    [["text" => "📮 ⌯ الدعم المباشر", "url" => "https://t.me/haamadh"]],
                    [["text" => "🚦 ⌯ قناة البوت", "url" => "https://t.me/+1ptMBPwAaXQ2Mjc0"]]
                ]
            ])
        ]);
    }
}

if (isset($hamadh6) && file_exists("do/$hamadh12.txt") && $hamadh14 == $hamadh15) {
    $hamadh24 = file_get_contents("do/$hamadh12.txt");
    
    if ($hamadh24 == "addcountry") {
        $hamadh25 = explode("\n", $hamadh6);
        if (count($hamadh25) >= 3) {
            $hamadh26 = trim($hamadh25[0]);
            $hamadh27 = trim($hamadh25[1]);
            $hamadh28 = trim($hamadh25[2]);
            
            $hamadh76_data = json_decode(file_get_contents($hamadh76), true);
            $hamadh76_data[] = ["name" => $hamadh26, "code" => $hamadh27, "price" => $hamadh28];
            file_put_contents($hamadh76, json_encode($hamadh76_data));
            
            unlink("do/$hamadh12.txt");
            hamadh('sendMessage', [
                'chat_id' => $hamadh12,
                'text' => "*✅ ⌯ تم اضافة الدولة ($hamadh26) بنجاح*",
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "رجوع", "callback_data" => "adminback"]]
                    ]
                ])
            ]);
        }
    }
    
    if ($hamadh24 == "set_user_join_channel") {
        hamadh127("user_join", $hamadh6);
        unlink("do/$hamadh12.txt");
        hamadh('sendMessage', [
            'chat_id' => $hamadh12,
            'text' => "*✅ ⌯ تم تعيين قناة دخول المستخدمين:* `$hamadh6`",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "رجوع", "callback_data" => "notification_channels"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh24 == "set_otp_received_channel") {
        hamadh127("otp_received", $hamadh6);
        unlink("do/$hamadh12.txt");
        hamadh('sendMessage', [
            'chat_id' => $hamadh12,
            'text' => "*✅ ⌯ تم تعيين قناة وصول الكود:* `$hamadh6`",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "رجوع", "callback_data" => "notification_channels"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh24 == "set_incomplete_orders_channel") {
        hamadh127("incomplete_orders", $hamadh6);
        unlink("do/$hamadh12.txt");
        hamadh('sendMessage', [
            'chat_id' => $hamadh12,
            'text' => "*✅ ⌯ تم تعيين قناة الأرقام غير المكتملة:* `$hamadh6`",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "رجوع", "callback_data" => "notification_channels"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh24 == "set_activations_channel") {
        hamadh127("activations", $hamadh6);
        unlink("do/$hamadh12.txt");
        hamadh('sendMessage', [
            'chat_id' => $hamadh12,
            'text' => "*✅ ⌯ تم تعيين قناة التفعيلات:* `$hamadh6`",
            'parse_mode' => "markdown",
            'reply_markup' => json_encode([
                'inline_keyboard' => [
                    [["text" => "رجوع", "callback_data" => "notification_channels"]]
                ]
            ])
        ]);
    }
    
    if ($hamadh24 == "banuser") {
        $hamadh200 = intval($hamadh6);
        if ($hamadh200 > 0) {
            if (hamadh86($hamadh200)) {
                $hamadh201 = "*✅ ⌯ تم حظر المستخدم $hamadh200 بنجاح*";
            } else {
                $hamadh201 = "*❌ ⌯ المستخدم $hamadh200 محظور مسبقاً*";
            }
            unlink("do/$hamadh12.txt");
            hamadh('sendMessage', [
                'chat_id' => $hamadh12,
                'text' => $hamadh201,
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "رجوع", "callback_data" => "adminback"]]
                    ]
                ])
            ]);
        }
    }
    
    if ($hamadh24 == "unbanuser") {
        $hamadh200 = intval($hamadh6);
        if ($hamadh200 > 0) {
            if (hamadh88($hamadh200)) {
                $hamadh201 = "*✅ ⌯ تم فك حظر المستخدم $hamadh200 بنجاح*";
            } else {
                $hamadh201 = "*❌ ⌯ المستخدم $hamadh200 غير محظور*";
            }
            unlink("do/$hamadh12.txt");
            hamadh('sendMessage', [
                'chat_id' => $hamadh12,
                'text' => $hamadh201,
                'parse_mode' => "markdown",
                'reply_markup' => json_encode([
                    'inline_keyboard' => [
                        [["text" => "رجوع", "callback_data" => "adminback"]]
                    ]
                ])
            ]);
        }
    }
}

$footer = "\n\n*➖ ⌯ حقوق برمجة وتجهيز ل { @bodic3 } ليس مسموح سرقة الحقوق ⚠️*";

if (isset($ABDU) && !empty($footer)) {
    hamadh('answerCallbackQuery', [
        'callback_query_id' => $update['callback_query']['id'],
        'text' => "✅ تمت العملية",
        'show_alert' => false
    ]);
}
//━━━━━━━━━━━━━━━━━━━━━━━━━━
//  © حـقـوق وڪـتـابـه الــمـبـرمـج
//  Telegram : @bodic3
//  Channel  : https://t.me/V_0_I_D_1
//━━━━━━━━━━━━━━━━━━━━━━━━━━
