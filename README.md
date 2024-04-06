# EEG Preprocessing & Classification


Data -> mat file 

1st step : transform .mat file to raw file (use MNE-Python)

2nd step:  bad _channels remove and interpolation 

3rd step : SVM classification



# 1st step

transform mat file

1. use MNE-Python Method : mne.create_info()  and mne.it.RawArray()


# 2nd step

bad_channels interpolation

1. use MNE-Python Method :mne.preprocessing.find_bad_channels_maxwell

2. Use visually detected
   -> raw.info['bads'].extend(channels)
   
   -> raw.interpolate_bads()
   
   -> raw.filter(l_freq = , h_freq)


4. Median
   
   -> raw_data transforms to numpy
   
   -> n_data[ch_names].rolling().median()
   
   -> df[col] = df[col].bfill()
   
        # 앞쪽 값으로 뒤쪽의 결측값 채우기
        df[col] = df[col].ffill()
   
   -> data_interpolated = df.to_numpy().T
   
       data[data_num]._data = data_interpolated

# 3rd step

1. use sklearn SVM
   

