# Slot Games Test Cases

## 1. Game Opening

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-001 | Verify game opens successfully on desktop | Player is logged in and has access to the selected game. Supported desktop browser is used. | 1. Open the game launch page.<br>2. Select the required game.<br>3. Open the game.<br>4. Wait for the game to finish loading. | The game opens successfully without errors. |
| TC-003 | Verify game loads completely without errors | Player is logged in and has access to the selected game. Stable internet connection is available. | 1. Open the selected game.<br>2. Wait until the game finishes loading.<br>3. Observe the game interface. | The game loads completely without a stuck loading screen, blank screen, missing elements, or unexpected error messages. |
| TC-004 | Verify game UI is displayed correctly after opening | Player is logged in and the selected game is available. | 1. Open the game.<br>2. Wait until the game is fully loaded.<br>3. Check the game interface. | All applicable UI elements are displayed correctly, including reels, symbols, Spin button, bet controls, balance, settings, and other available controls. No elements are overlapping, cut off, or incorrectly positioned. |
| TC-005 | Verify player balance is displayed correctly when opening the game | Player is logged in and has a known account balance. | 1. Note the player's balance before opening the game.<br>2. Open the selected game.<br>3. Check the balance displayed inside the game. | The balance displayed inside the game matches the player's actual account balance. |
| TC-006 | Verify correct currency is displayed when opening the game | Player is logged in and has a configured account currency. | 1. Open the selected game.<br>2. Check the currency displayed in the game. | The player's configured account currency is displayed correctly in the game. |
| TC-007 | Verify default bet amount is displayed correctly when opening the game | Player is logged in. The game has a configured default bet amount. | 1. Open the selected game.<br>2. Check the displayed bet amount. | The correct default bet amount is displayed when the game is opened and is available for placing a bet. |
| TC-008 | Verify game can be opened from the game lobby | Player is logged in. The selected game is available in the game lobby. | 1. Navigate to the game lobby.<br>2. Locate the selected game.<br>3. Click/tap the game.<br>4. Wait for the game to load. | The selected game opens successfully and the player is not redirected to an incorrect game or page. |
| TC-009 | Verify game opens successfully using the direct game URL | Player is logged in and has access to the selected game. A valid game URL is available. | 1. Open the game URL in a supported browser.<br>2. Wait for the game to load. | The correct game opens successfully and all applicable game information is loaded correctly. |

## 2. Place a Bet — Balance & Deduction Accuracy

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-010 | Correct deduction on valid bet | — | Place a bet of a fixed amount (e.g., 10) with sufficient balance. | Balance reduces by exactly the bet amount; new balance = old balance − bet. |
| TC-011 | Deduction reflects immediately in UI | — | Place a bet and observe the balance display. | Balance updates in real time without needing refresh/reload. |
| TC-012 | Multiple sequential bets | — | Place several bets in a row. | Each bet deducts correctly; cumulative deduction = sum of all bets. |
| TC-013 | Min bet deduction | — | Place the minimum allowed bet. | Correct minimum amount is deducted. |
| TC-014 | Max bet deduction | — | Place the maximum allowed bet. | Correct maximum amount is deducted, with no overflow errors. |

## 3. Place a Bet — Winning

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-015 | Balance unchanged when no win | — | Play a round with no win. | No win popup/animation appears; UI returns to idle state normally. |
| TC-016 | Balance updates only after animation completes | — | Win a round with animation. | Win amount transfers after the animation ends. |
| TC-017 | Balance updates without requiring manual refresh | — | Win a round. | Balance updates automatically in real time; no page/app refresh is needed. |
| TC-018 | Balance updates before next bet is allowed | — | Win a round and attempt to place the next bet immediately. | Next bet uses the updated post-win balance, not the stale pre-win balance. |

## 4. Place a Bet — Insufficient Funds Handling

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-019 | Bet greater than balance | — | Attempt to bet more than the current balance. | Bet is rejected; an error message is shown; no deduction occurs. |
| TC-020 | Bet exactly equal to balance | — | Bet the full remaining balance. | Bet is accepted; balance becomes 0; balance does not become negative. |
| TC-021 | Zero balance bet attempt | Balance = 0. | Attempt any bet. | Bet is blocked; a deposit/top-up prompt is shown. |
| TC-022 | Balance depleted mid-session | — | Play until the balance hits 0 during a round. | Game gracefully stops accepting further bets; an appropriate message is displayed. |
| TC-023 | Bet below minimum limit | — | Enter a bet amount lower than the game's minimum. | Bet is rejected with a validation message; no deduction occurs. |
| TC-024 | Bet above table/game max limit, entering manually | — | Enter a bet exceeding the maximum limit. | Bet is rejected; no deduction occurs, and the maximum bet amount is returned/displayed. |
| TC-025 | Negative bet amount | — | Manually input a negative value. | Request is rejected; no deduction occurs. |

## 5. Place a Bet — Timing

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-026 | Double-click / rapid bet submission | — | Click "Place Bet" multiple times quickly. | Only one deduction occurs per intended bet; no duplicate charges occur. |
| TC-027 | Concurrent bets across multiple tabs/devices | — | Log in on two sessions and place bets simultaneously. | Balance updates consistently across sessions; no race condition allows an overdraft. |

## 6. Place a Bet — Post-Bet / Rollback Scenarios

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-028 | Bet cancelled before round starts (if allowed), e.g. Aviator | Cancellation is supported by the game. | Place a bet, then cancel within the allowed window. | Full amount is refunded/restored to the balance. |
| TC-029 | Round fails to start after deduction | — | Simulate a game engine failure after the bet is deducted. | System automatically refunds the deducted amount. |

## 7. Place a Bet — Game History

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-030 | Balance history/statement accuracy | — | Place several bets and check the transaction history page. | All deductions are listed accurately in chronological order. |

## 8. Demo/Real — Mode Switch

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-031 | Launch game in demo mode | — | Open the game via the "Demo" option. | Game launches successfully in demo mode; demo indicator is visible. |
| TC-032 | Launch game in real money mode | — | Open the game via the "Real Money" option. | Game launches successfully in real mode; real balance is displayed. |
| TC-033 | Switch from demo to real mode mid-session | Game is in demo mode. | Select the "Real" option. | Game reloads/switches into real mode correctly; demo balance is discarded. |
| TC-034 | Switch from real to demo mode mid-session | Game is in real mode. | Select the "Play for Fun/Demo" option. | Game reloads/switches into demo mode correctly; real balance is not affected. |

## 9. Demo/Real — Balance Handling During Switch

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-035 | Demo balance is separate from real balance | — | Play in demo mode, note the demo balance, then switch to real mode. | Real balance shown is unaffected by demo balance/activity. |
| TC-036 | Demo balance resets appropriately | — | Play in demo mode, spend/win virtual credits, switch away, and return to demo mode. | Demo balance resets to the default starting value, according to game design. |
| TC-037 | Real balance persists correctly after switching from demo | — | Play in demo mode, then switch to real mode. | Real balance shown matches the actual wallet balance; there is no demo contamination. |
| TC-038 | No real funds used while in demo mode | — | Play multiple rounds in demo mode. | Real wallet balance remains completely untouched throughout. |
| TC-039 | Switching modes does not carry over bet amount incorrectly | — | Set a specific bet amount in demo mode, then switch to real mode. | Bet amount either resets to default or carries over correctly according to game design; verify the intended behavior. |
| TC-040 | Autoplay stops when switching modes | — | Enable autoplay in one mode and attempt to switch modes. | Autoplay stops automatically before/during the switch. |
| TC-041 | Switching mode with insufficient real balance | Real balance is zero or low. | Switch from demo to real mode. | Real mode still loads correctly; a deposit prompt is shown if the balance is 0; no crash occurs. |
| TC-042 | Rapid repeated mode switching | — | Quickly switch between demo and real mode multiple times. | No crashes, freezes, or balance/state corruption occur from rapid toggling. |

## 10. Music/Audio — Turn On/Off

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-043 | Background music plays on game launch | — | Open the game. | Background music starts playing automatically, or according to platform autoplay policy. |
| TC-044 | Win sound plays on win | — | Trigger a winning round. | Win sound effect plays, matching the win tier (small/medium/big win). |
| TC-045 | Sound effect plays on game launch | — | Open the game and spin once. | After the spin, there should be sound in slot games. |
| TC-046 | Big win/mega win celebration sound | — | Trigger a large win. | Special big-win sound/fanfare plays, distinct from the regular win sound. |
| TC-047 | Mute all sound via master toggle | — | Tap the mute/sound icon. | All sound (music and effects) stops immediately. |
| TC-048 | Unmute restores all sound | Sound is muted. | Tap the mute icon again to unmute. | All sound resumes correctly; music and effects both return. |
| TC-049 | Mute background music only | A separate music control exists. | Mute music only. | Music stops; sound effects (spin, win, click) still play. |
| TC-050 | Mute sound effects only | A separate sound-effects control exists. | Mute SFX only. | Sound effects stop; background music continues playing. |
| TC-051 | Mute state during active spin | — | Mute sound while reels are spinning. | Sound cuts off immediately without glitches or cutoff artifacts. |
| TC-052 | Volume set to max does not distort/clip | — | Set volume to maximum. | Sound plays clearly without distortion, crackling, or clipping. |
| TC-053 | Change sound volume (background, sound effects) | — | Change sound levels to minimum, middle, and maximum. | Sound volume changes according to the selected level. |
| TC-054 | Sound setting persists after closing and reopening game | — | Mute sound, close the game, and reopen it. | Game reopens with sound still muted, depending on game rules. |
| TC-055 | Sound setting persists across different games | — | Mute sound in Game A, then open Game B from the same provider/lobby. | Mute setting carries over to Game B. |
| TC-056 | Sound setting resets appropriately per device (if device-specific) | — | Mute sound on Device A, then check Device B. | Setting is independent per device or synced per account according to the intended design; verify consistency. |
| TC-057 | Sound works correctly with Bluetooth/wired headphones | Headphones are connected. | Connect headphones and play the game. | Audio routes correctly through headphones, with no delay or dropout. |
| TC-058 | Sound behavior during phone call interruption (mobile) | Game is running on a mobile device. | Receive a call while playing. | Game audio pauses appropriately during the call and resumes after the call ends. |

## 11. Cross-Browser Compatibility

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-059 | Game loads on Google Chrome | — | Open the game on the latest Chrome version. | Game loads fully, all assets render, and the game is fully playable. |
| TC-060 | Game loads on Mozilla Firefox | — | Open the game on the latest Firefox version. | Game loads fully, all assets render, and the game is fully playable. |
| TC-061 | Game loads on Safari | — | Open the game on the latest Safari version (Mac/iOS). | Game loads fully, all assets render, and the game is fully playable. |
| TC-062 | Game loads on Microsoft Edge | — | Open the game on the latest Edge version. | Game loads fully, all assets render, and the game is fully playable. |
| TC-063 | Game loads on Opera | — | Open the game on the latest Opera version. | Game loads fully, all assets render, and the game is fully playable. |
| TC-064 | Game on older browser version, if possible | An older but supported browser version is available. | Open the game in an older but still supported browser version. | Game loads with acceptable performance and no critical feature breakage. |
| TC-065 | In-private/incognito mode compatibility | — | Open the game in incognito/private browsing mode. | Game loads and functions correctly, with no broken storage-dependent features. |
| TC-066 | Browser zoom in/out | — | Zoom the browser to 50%, 100%, 150%, and 200%. | UI scales or adjusts without breaking the layout; elements are not cut off or overlapping. |
| TC-067 | Multiple browser tabs open simultaneously | — | Open the same game in two tabs of the same browser. | Error message "multiple session not allowed" is displayed. |
| TC-068 | Browser refresh mid-session | A game session is active. | Refresh the page while playing. | Game reloads cleanly; session/balance state recovers correctly. |

## 12. Device Compatibility

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-069 | Game loads on Android phone (various OEMs) | Supported Android devices are available. | Test on Samsung, Google Pixel, Xiaomi, etc. | Game loads and plays correctly across different Android devices. |
| TC-070 | Game loads on iPhone (various models) | Supported iPhone models are available. | Test on latest and older supported iPhone models. | Game loads and plays correctly across iPhone models. |
| TC-071 | Game loads on Android tablet | Android tablet is available. | Open the game on an Android tablet. | UI adapts correctly to tablet screen size; game is fully playable. |
| TC-072 | Game loads on iPad | iPad is available. | Open the game on an iPad. | UI adapts correctly to iPad screen size; game is fully playable. |
| TC-073 | Interruption handling — incoming call | Game is running on a mobile device. | Receive a call while playing. | Game pauses/handles the interruption gracefully and resumes correctly afterward. |
| TC-074 | Interruption handling — notification pull-down | Game is running on a mobile device. | Pull down the notification shade mid-game. | Game state remains intact when returning to the game. |
| TC-075 | Low battery mode | — | Enable low power/battery saver mode and play the game. | Game remains functional, possibly with reduced animations, and does not crash. |
| TC-076 | Mobile data vs Wi-Fi | — | Play the game on mobile data, then switch to Wi-Fi mid-session. | Game continues functioning smoothly across the network type switch. |

## 13. Localization / Multi-language

| TC ID | Test Case Name | Preconditions | Steps | Expected Result |
|---|---|---|---|---|
| TC-077 | Language selector is accessible | — | Open settings/menu and locate the language option. | Language selector is easy to find and opens correctly. |
| TC-078 | Default language matches account/browser setting | Account or browser language setting is configured. | Open the game without manually selecting a language. | Game loads in the correct default language based on the account setting or browser locale. |
| TC-079 | Switching language updates UI text | Multiple languages are available. | Select a different language from the list. | All visible text (buttons, menus, labels) updates to the selected language. |
| TC-080 | Language setting persists after reload | A language has been selected. | Switch language and refresh the page/app. | Selected language remains active after reload. |
| TC-081 | Win/loss messages translated | A language other than the default is selected. | Trigger a win and a loss. | Win/loss popup text is displayed in the correct language. |
| TC-082 | Error messages translated | A language is selected. | Trigger an error, e.g. insufficient balance. | Error message is shown in the correct selected language. |
| TC-083 | Date/time format matches locale (in history) | — | Check timestamps in transaction history. | Date/time is displayed in the correct regional format (DD/MM vs MM/DD, 12-hour vs 24-hour). |
| TC-084 | Sound/voiceover localization (if applicable) | The game has voiceovers in multiple languages. | Switch to a language where the game has voiceovers. | Voice/audio cues match the selected language. |
| TC-085 | Language switch mid-session | A game session is active. | Change language while actively playing. | UI updates immediately without requiring a full game restart, or reloads cleanly if restart is by design. |
| TC-086 | Consistent language across game and lobby/platform | — | Change the game from the game lobby. | Changing the game from the lobby should affect another game. |
| TC-087 | Currency mismatch with language | Account currency is configured. | Select a language whose region typically uses a different currency than the account's actual currency. | Language and currency remain correctly independent; game currency does not change just because the language changed. |
| TC-088 | Language persists through demo/real mode switch | A language has been selected. | Switch language, then switch between demo and real mode. | Language setting remains consistent across both modes. |
| TC-089 | No mixed-language text in a single screen | A language has been selected. | Check each screen carefully after switching language. | No screen shows a mix of two languages simultaneously, which would indicate incomplete translation loading. |

