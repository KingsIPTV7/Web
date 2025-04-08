import React, { useEffect, useRef, useState } from 'react';
import Hls from 'hls.js';
import { Play, Pause, SkipForward, SkipBack } from 'lucide-react';

// Dummy M3U Playlist Content (You can fetch this from a URL or upload)
const sampleM3U = 
#EXTM3U
#EXTINF:-1 tvg-id="vid1" tvg-name="Video 1",Video 1
https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8
#EXTINF:-1 tvg-id="vid2" tvg-name="Video 2",Video 2
https://test-streams.mux.dev/test_001/stream.m3u8
;

function parseM3U(m3uContent) {
  const lines = m3uContent.trim().split('\n');
  const list = [];
  for (let i = 0; i < lines.length; i++) {
    if (lines[i].startsWith('#EXTINF')) {
      const title = lines[i].split(',')[1]?.trim() || Video ${i};
      const src = lines[i + 1]?.trim();
      if (src) list.push({ title, src });
    }
  }
  return list;
}

export default function WebPlayer() {
  const videoRef = useRef(null);
  const [playlist, setPlaylist] = useState([]);
  const [currentIndex, setCurrentIndex] = useState(0);
  const [playing, setPlaying] = useState(false);

  useEffect(() => {
    const parsed = parseM3U(sampleM3U);
    setPlaylist(parsed);
  }, []);

  useEffect(() => {
    const video = videoRef.current;
    if (playlist.length === 0 || !video) return;

    if (Hls.isSupported()) {
      const hls = new Hls();
      hls.loadSource(playlist[currentIndex].src);
      hls.attachMedia(video);
      hls.on(Hls.Events.MANIFEST_PARSED, () => {
        if (playing) video.play();
      });

      return () => {
        hls.destroy();
      };
    } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
      video.src = playlist[currentIndex].src;
      if (playing) video.play();
    }
  }, [currentIndex, playlist, playing]);

  const togglePlay = () => {
    const video = videoRef.current;
    if (!video) return;

    if (video.paused) {
      video.play();
      setPlaying(true);
    } else {
      video.pause();
      setPlaying(false);
    }
  };

  const nextVideo = () => setCurrentIndex((i) => (i + 1) % playlist.length);
  const prevVideo = () => setCurrentIndex((i) => (i - 1 + playlist.length) % playlist.length);

  return (
    <div className="max-w-3xl mx-auto mt-10 p-4 bg-gray-900 text-white rounded-2xl shadow-lg">
      <h1 className="text-2xl font-bold mb-4">
        {playlist[currentIndex]?.title || 'Loading...'}
      </h1>

      <div className="bg-black rounded-xl overflow-hidden mb-4">
        <video
          ref={videoRef}
          className="w-full"
          controls
          crossOrigin="anonymous"
          playsInline
          airplay="allow"
        >
          <track
            kind="subtitles"
            src="https://gist.githubusercontent.com/samdutton/ca37f3adaf4e23679957b8083e061177/raw/e19399fbccbc069a2af4266e5120ae6bad62699a/sample.vtt"
            srcLang="en"
            label="English"
            default
          />
        </video>
      </div>

      <div className="flex justify-center items-center gap-4">
        <button onClick={prevVideo} className="bg-gray-700 p-2 rounded-xl hover:bg-gray-600">
          <SkipBack />
        </button>
        <button onClick={togglePlay} className="bg-blue-600 p-2 rounded-xl hover:bg-blue-500">
          {playing ? <Pause /> : <Play />}
        </button>
        <button onClick={nextVideo} className="bg-gray-700 p-2 rounded-xl hover:bg-gray-600">
          <SkipForward />
        </button>
      </div>
    </div>
  );
}
