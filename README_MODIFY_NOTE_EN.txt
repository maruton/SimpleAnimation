*** Modify version
This is Modify version.
Distributed under the original license. Please read included file 'LICENSE'.

The original version is below.
https://github.com/Unity-Technologies/SimpleAnimation


*** What modify
*Add new method.

File: SimpleAnimation.cs
isPlayEnd()
	Get playing animation status.
	IN: (string)stateName
	RET:(bool) True is play end.  False is still playing.


GetNormalizeTime()
	Get playing animation laptime. value is normalized.
	IN: (string)stateName
	RET:(float)Normalized animation playing time(0.0 to 1.0).

SetSpeed()
	Set animation playing speed.
	IN: (string)stateName, (float)speed
		Set playback Animation speed. less is slow, greater is fast.


*Fixed obsolete / deprecated methods 
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

