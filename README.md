# convert-string-to-nfc-ndef-message

import android.nfc.NdefRecord;

public static NdefRecord getMediaRecord(String messageToWrite,
                                        String type) {

    byte[] textBytes = messageToWrite.getBytes();
    NdefRecord textRecord = new NdefRecord(NdefRecord.TNF_MIME_MEDIA,
            type.getBytes(), new byte[] {}, textBytes);
    return textRecord;
}

// this will print the ndef message and you can then pass it via nfc
System.out.println(getMediaRecord( "nigel reign", "bytes" ));
