package android.com.dropdownexample;

import android.app.Dialog;
import android.app.DialogFragment;
import android.content.DialogInterface;
import android.os.Bundle;
import android.support.v7.app.AlertDialog;

/**
 * Created by Shahkar Raza on 26-Nov-16.
 */

public class AlertBusiness extends DialogFragment {

    AlertPositiveListener alertPositiveListener;

    public interface AlertPositiveListener {
        public void onPositiveClick(int position);
    }
    public void onAttach(android.app.Activity activity) {
        super.onAttach(activity);
        try{
            alertPositiveListener = (AlertPositiveListener) activity;
        }catch(ClassCastException e){
            // The hosting activity does not implemented the interface AlertPositiveListener
            throw new ClassCastException(activity.toString() + " must implement AlertPositiveListener");
        }
    }
    DialogInterface.OnClickListener positiveListener = new DialogInterface.OnClickListener() {
        @Override
        public void onClick(DialogInterface dialog, int which) {
            AlertDialog alert = (AlertDialog)dialog;
            int position = alert.getListView().getCheckedItemPosition();
            alertPositiveListener.onPositiveClick(position);
        }
    };

    @Override
    public Dialog onCreateDialog(Bundle savedInstanceState) {
        Bundle bundle = getArguments();
        int position = bundle.getInt("position");
        AlertDialog.Builder b = new AlertDialog.Builder(getActivity());
        b.setTitle(" Choose your Car");
        b.setSingleChoiceItems(Business.cars, position, null);
        b.setPositiveButton("OK",positiveListener);
        b.setNegativeButton("Cancel", null);
        AlertDialog d = b.create();
        return d;
    }
}

