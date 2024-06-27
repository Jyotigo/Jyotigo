bool checkOtherState(int mode, e_ModuleState state, e_ModuleState *i_pProcess[], short int i_wProcessNbr) {
    int i_i = 0 ;
    int i_cnt = 0 ;

    if (mode == 1) 
    { //
        for (i_i = 0; i_i < i_wProcessNbr; i_i++) 
        { /* Boucle venant vérifier l?état processus */
            if ((*i_pProcess[i_i]) == state)
            {
                i_cnt++ ;
            }
        }

        if (i_cnt == i_wProcessNbr) 
        { /* test si tous les process testés sont dans le bon état */
            return 1 ;
        } 
        else 
        {
            return 0 ;
        }
    } 
    else 
    {
        for (i_i = 0; i_i < i_wProcessNbr; i_i++)
        {
            if ((*i_pProcess[i_i]) != state)
            { /* Si un process n'est pas dans le bon état */
                return 1 ;
            }
        }
        return 0 ;
    }
}
