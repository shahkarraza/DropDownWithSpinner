package android.com.dropdownexample;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.Spinner;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity implements AlertEconomy.AlertPositiveListener,AlertBusiness.AlertPositiveListener {


    private Spinner spinner;
    int position = 0;
    private android.app.FragmentManager economy_manager, business_manager;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        spinner=(Spinner)findViewById(R.id.spinner);
        spinner.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {
            @Override
            public void onItemSelected(AdapterView<?> adapterView, View view, int i, long l) {
                switch (i){
                    case 0:

                        break;

                    case 1:
                        economy_manager= getFragmentManager();
                        AlertEconomy economy= new AlertEconomy();
                        Bundle eco= new Bundle();
                        eco.putInt("position",position);
                        economy.setArguments(eco);
                        economy.show(economy_manager,"alert_dialog_radio");
                        break;
                    case 2:
                        business_manager= getFragmentManager();
                        AlertBusiness business= new AlertBusiness();
                        Bundle busi= new Bundle();
                        busi.putInt("position",position);
                        business.setArguments(busi);
                        business.show(business_manager,"alert_dialog_radio");
                        break;

                }

            }

            @Override
            public void onNothingSelected(AdapterView<?> adapterView) {

            }
        });
    }

    @Override
    public void onPositiveClick(int position) {
        this.position= position;

        Toast.makeText(this, "Your Choice is " + Economy.cars[this.position], Toast.LENGTH_LONG).show();

    }
}
