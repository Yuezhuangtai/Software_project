Num_Array=['0','1','2','3','4','5','6','7','8','9','.','+','-','*','/','^','(',')']
Mathe_symbol=['+','-','*','/','^','(',')']

def Det_decimals(formula):
    "判断小数，返回它的小数点位置和小数的起始点和终止点"
    Record={}
    left_bound=right_bound=0
    for count in range(len(formula)):
        if formula[count] =='.':
            left_bound = count - 1
            right_bound = count + 1
            while formula[left_bound] not in Mathe_symbol:
                if left_bound != 0:
                    left_bound-=1
                else:
                    break
            while formula[right_bound] not in Mathe_symbol:
                if right_bound != len(formula)-1:
                    right_bound+=1
                else:
                    break
            if right_bound!=len(formula)-1:
                right_bound-=1
            if left_bound !=0:
                left_bound+=1
            Record[count]=[left_bound,right_bound]
        left_bound = right_bound = 0
    return Record
def Data_Divided(formula):
    Formula_list=[]
    "小数预处理"
    Decimals_dic=Det_decimals(formula)
    print(Decimals_dic)
    dic_count=0
    Temp=None
    for count in range(len(formula)):
        print(Decimals_dic[dic_count][0])
    #     if  count<Decimals_dic[dic_count][0]:
    #         Formula_list=formula[count]
    #     elif Decimals_dic[dic_count][0]==count:
    #         Formula_list=formula[Decimals_dic[dic_count][0]]+formula[Decimals_dic[dic_count][1]]
    #         for Dec_count in range(formula[Decimals_dic[dic_count][1]]-formula[Decimals_dic[dic_count][0]]):
    #             Temp=formula[Decimals_dic[dic_count][0]]+Temp
    #         Formula_list=Temp
    #         dic_count +=1
    #     else:
    #         count = formula[Decimals_dic[dic_count][0]]
    # return  Formula_list
def Detection_Cal(formula):
    Det_Obj=formula
    Error_Judge=0
    for Count in range(len(Det_Obj)):
        if Det_Obj[Count] not in Num_Array :
            Error_Judge=1

    if Error_Judge==1:
        print("INPUT ERROR")



Obj_formula=input()
Detection_Cal(Obj_formula)
# info=Det_decimals(Obj_formula)
# print(info)
Data_Divided(Obj_formula)
