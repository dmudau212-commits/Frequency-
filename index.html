package com.ambisonic.frequencymatrix;

import android.app.Notification;
import android.app.NotificationChannel;
import android.app.NotificationManager;
import android.app.Service;
import android.content.Context;
import android.content.Intent;
import android.media.AudioAttributes;
import android.media.AudioFocusRequest;
import android.media.AudioManager;
import android.os.Build;
import android.os.IBinder;

public class AudioMatrixService extends Service {
    private AudioManager audioManager;
    private AudioFocusRequest focusRequest;

    @Override
    public void onCreate() {
        super.onCreate();
        audioManager = (AudioManager) getSystemService(Context.AUDIO_SERVICE);
        startForegroundServiceNotification();
    }

    @Override
    public int onStartCommand(Intent intent, int flags, int startId) {
        // Request System Audio Focus with "TRANSIENT_MAY_DUCK"
        // This forces other apps (like games or videos) to automatically lower their volume
        // so your background music track can sit perfectly balanced underneath them.
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
            focusRequest = new AudioFocusRequest.Builder(AudioManager.AUDIOFOCUS_GAIN_TRANSIENT_MAY_DUCK)
                    .setAudioAttributes(new AudioAttributes.Builder()
                            .setUsage(AudioAttributes.USAGE_MEDIA)
                            .setContentType(AudioAttributes.CONTENT_TYPE_MUSIC)
                            .build())
                    .setOnAudioFocusChangeListener(focusChange -> {
                        // Handle real-time system audio shifts here
                    })
                    .build();

            audioManager.requestAudioFocus(focusRequest);
        }
        return START_STICKY;
    }

    private void startForegroundServiceNotification() {
        String CHANNEL_ID = "matrix_audio_channel";
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
            NotificationChannel channel = new NotificationChannel(CHANNEL_ID,
                    "Matrix Core Audio Engine", NotificationManager.IMPORTANCE_LOW);
            ((NotificationManager) getSystemService(NotificationManager.class)).createNotificationChannel(channel);
        }

        Notification notification = null;
        if (android.os.Build.VERSION.SDK_INT >= android.os.Build.VERSION_CODES.O) {
            notification = new Notification.Builder(this, CHANNEL_ID)
                    .setContentTitle("AMBISONIC CORE IS ACTIVE")
                    .setContentText("Frequency isolation matrix running in background...")
                    .build();
        }
        startForeground(1, notification);
    }

    @Override
    public IBinder onBind(Intent intent) { 
        return null; 
    }
}
