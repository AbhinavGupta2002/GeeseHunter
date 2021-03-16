//
//  ViewController.swift
//  Geese Hunter
//
//  Created by Abhinav Gupta on 15/03/2021.
//

import UIKit
import AVFoundation

class MusicHelper {
    static let sharedHelper = MusicHelper()
    var audioPlayer: AVAudioPlayer?
    
    func playBackgroundMusic(song: String, type: String, loop: Bool) {
        let aSound = NSURL(fileURLWithPath: Bundle.main.path(forResource: song, ofType: type)!)
        do {
            audioPlayer = try AVAudioPlayer(contentsOf:aSound as URL)
            if (loop == true) {
                audioPlayer!.numberOfLoops = -1
            } else {
                audioPlayer!.numberOfLoops = 0
            }
            audioPlayer!.prepareToPlay()
            audioPlayer!.play()
        } catch {
            print("Cannot play the file")
        }
    }
}

class ViewController: UIViewController {
    @IBOutlet weak var below_timer_lbl: UILabel!
    @IBOutlet weak var start_button: UIButton!
    @IBOutlet weak var play_again: UIButton!
    @IBOutlet weak var title2: UILabel!
    @IBOutlet weak var title3: UILabel!
    @IBOutlet weak var title1: UILabel!
    @IBOutlet weak var Geese_Counter: UILabel!
    @IBOutlet weak var Geese_Counter_lbl: UILabel!
    @IBOutlet weak var seconds_lbl: UILabel!
    @IBOutlet weak var Goose1: UIButton!
    @IBOutlet weak var Goose2: UIButton!
    @IBOutlet weak var Goose3: UIButton!
    @IBOutlet weak var Goose4: UIButton!
    @IBOutlet weak var Goose5: UIButton!
    @IBOutlet weak var Goose6: UIButton!
    @IBOutlet weak var Goose7: UIButton!
    @IBOutlet weak var Goose8: UIButton!
    @IBOutlet weak var Goose9: UIButton!
    @IBOutlet weak var Goose10: UIButton!
    @IBOutlet weak var Goose11: UIButton!
    @IBOutlet weak var Goose12: UIButton!
    @IBOutlet weak var Goose13: UIButton!
    @IBOutlet weak var Goose14: UIButton!
    @IBOutlet weak var Goose15: UIButton!
    @IBOutlet weak var Goose16: UIButton!
    @IBOutlet weak var Goose17: UIButton!
    @IBOutlet weak var Goose18: UIButton!
    @IBOutlet weak var Goose19: UIButton!
    @IBOutlet weak var Goose20: UIButton!
    
    var time = 0
    var timer = Timer()
    let geese:Int = 30 // number of geese to catch
    var curr_geese = 30
    var prev_goose = -1
    var count_time = 0
    var geese_heads: [UIButton] {
        return [self.Goose1, self.Goose2, self.Goose3, self.Goose4, self.Goose5, self.Goose6, self.Goose7, self.Goose8, self.Goose9, self.Goose10, self.Goose11, self.Goose12, self.Goose13, self.Goose14, self.Goose15, self.Goose16, self.Goose17, self.Goose18, self.Goose19, self.Goose20]
    }

    
    @IBAction func playAgain(_ sender: Any) {
        MusicHelper.sharedHelper.playBackgroundMusic(song: "Hunted_Goose", type: "wav", loop: false)
        play_again.isHidden = true
        curr_geese = geese
        prev_goose = -1
        count_time = 0
        time = 0
        title1.text = "How fast"
        title2.text = "can you hunt"
        title3.text = "30 Geese?!"
        viewDidLoad()
        title3.isHidden = false
    }
    
    @IBAction func start(_ sender: UIButton) {
        MusicHelper.sharedHelper.playBackgroundMusic(song: "Hunted_Goose", type: "wav", loop: false)
        sender.isHidden = true
        title1.isHidden = true
        title2.isHidden = true
        title3.isHidden = true
        timer = Timer.scheduledTimer(timeInterval: 1, target: self, selector: #selector(ViewController.action), userInfo: nil, repeats: true)
        Geese_Counter.isHidden = false
        Geese_Counter_lbl.isHidden = false
        Geese_Counter.text = String(geese)
        let random_goose = Int.random(in: 0...19)
        geese_heads[random_goose].isHidden = false
        prev_goose = random_goose
    }
    
    @IBAction func goose(_ sender: UIButton) {
        MusicHelper.sharedHelper.playBackgroundMusic(song: "Goose_Honk", type: "mp3", loop: false)
        curr_geese -= 1
        Geese_Counter.text = String(curr_geese)
        geese_heads[prev_goose].isHidden = true
        let random_goose = Int.random(in: 0...19)
        geese_heads[random_goose].isHidden = false
        prev_goose = random_goose
        if (curr_geese <= 0) {
            Geese_Counter.text = "0"
            timer.invalidate()
            seconds_lbl.isHidden = true
            below_timer_lbl.isHidden = true
            geese_heads[prev_goose].isHidden = true
            title1.text = "You won in"
            title2.text = "\(count_time) seconds"
            title1.isHidden = false
            title2.isHidden = false
            MusicHelper.sharedHelper.playBackgroundMusic(song: "Game_Won", type: "wav", loop: false)
            play_again.isHidden = false
        }
    }
    
    @objc func action() {
        count_time += 1
        time += 1
        seconds_lbl.text = String(time)
    }
    
    override func viewDidLoad() {
        super.viewDidLoad()
        seconds_lbl.isHidden = false
        seconds_lbl.text = "0"
        start_button.isHidden = false
        play_again.isHidden = true
        Geese_Counter.isHidden = true
        Geese_Counter_lbl.isHidden = true
        below_timer_lbl.isHidden = false
        Goose1.isHidden = true
        Goose2.isHidden = true
        Goose3.isHidden = true
        Goose4.isHidden = true
        Goose5.isHidden = true
        Goose6.isHidden = true
        Goose7.isHidden = true
        Goose8.isHidden = true
        Goose9.isHidden = true
        Goose10.isHidden = true
        Goose11.isHidden = true
        Goose12.isHidden = true
        Goose13.isHidden = true
        Goose14.isHidden = true
        Goose15.isHidden = true
        Goose16.isHidden = true
        Goose17.isHidden = true
        Goose18.isHidden = true
        Goose19.isHidden = true
        Goose20.isHidden = true
    }
    
    override var shouldAutorotate: Bool { // for restricting to portrait mode
        return false
    }
    override var supportedInterfaceOrientations: UIInterfaceOrientationMask {
        return UIInterfaceOrientationMask.portrait
    }

    override var preferredInterfaceOrientationForPresentation: UIInterfaceOrientation {
        return UIInterfaceOrientation.portrait
    }
}

