<div align='center' ><font size='50'>Q1安卓版接口文档(draft)</font></div>

#### libScaleAPI.so
##### example:
```
int main()
{
    int ret = 0;
    int weight;
    int tare;
    int state;
    ret = bizlars_open();
    if( ret != true )
    {
        qDebug() << "bizlars_close() failed:" << ret << "......";
        return 1;
    }
    while(running)
    {
        ret = bizlars_readWeight(&weight,&tare,&state);
        
        ...
    }
    ret = bizlars_close();
    if( ret != true )
    {
        qDebug() << "bizlars_close() failed:" << ret << "......";
        return 1;
    }
    return 0;
}    
```

##### bizClars.h
```
/**
 * @brief    bizlars_open
 * 
 * 
 * @return   true -> success
 * @return   false -> failure
 * @remarks  open scale
 */
bool bizlars_open(void);
```

<div style="page-break-after: always"></div>

```

/**
 * @brief    bizlars_close
 * 
 * 
 * @return   true -> success
 * @return   false -> failure
 * @remarks  close scale
 */
bool bizlars_close(void);

/**
 * @brief    bizlars_readWeight
 * 
 * @param    weightOut -> weight value
 * @param    tareOut -> tare value
 * @param    state -> state value
 * 
 * @return   true -> success
 * @return   false -> failure
 * @remarks  read weight from scale
 */
bool bizlars_readWeight(int *weightOut, int *tareOut, int *state);

/**
 * @brief    bizlars_zeroScale
 * 
 * 
 * @return   true -> success
 * @return   false -> failure
 * @remarks  zero scale
 */
bool bizlars_zeroScale();

/**
 * @brief    bizlars_setTare
 * 
 * 
 * @return   true -> success
 * @return   false -> failure
 * @remarks  set tare according to weight on scale
 */
bool bizlars_setTare();

/**
 * @brief    bizlars_clearTare
 * 
 * 
 * @return   true -> success
 * @return   false -> failure
 * @remarks  clear tare
 */
bool bizlars_clearTare();
```