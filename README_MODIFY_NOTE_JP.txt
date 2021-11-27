*** 改変バージョン
これは改変バージョンです。
原本のライセンスに従い配布されています。ライセンスについては同梱の'LICENSE'ファイルを参照して下さい。

原本バージョンは以下。
https://github.com/Unity-Technologies/SimpleAnimation


*** 改変内容
■メソッドを追加

File: SimpleAnimation.cs
isPlayEnd()
	アニメーションの再生状態を取得。
	IN: (string)stateName
	RET:(bool) True 再生終了  False 再生中

GetNormalizeTime()
	アニメーションの再生時間位置をノーマライズした値で取得。
	IN: (string)stateName
	RET:(float)Normalized animation playing time(0.0 to 1.0).

SetSpeed()
	アニメーションの再生速度を指定。
	IN: (string)stateName, (float)speed
		Set playback Animation speed. less is slow, greater is fast.


File: SimpleAnimationPlayable_States.cs
■廃止/非推奨メソッドを修正
public void Pause()
        {
			// (DEL) m_Playable.SetPlayState(PlayState.Paused); // Obsolete: 'SetPlayState() has been deprecated. Use Play(), Pause() or SetDelay() instead'
			m_Playable.Pause(); // (ADD)
        }

        public void Play()
        {
            // (DEL) m_Playable.SetPlayState(PlayState.Playing); // Obsolete: 'SetPlayState() has been deprecated. Use Play(), Pause() or SetDelay() instead'
			m_Playable.Play(); // (ADD)
        }
