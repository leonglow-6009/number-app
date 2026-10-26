def generate_lucky_numbers(birth_year, ic_last_4):
    # 确保输入格式正确
    year_digits = [int(d) for d in str(birth_year)]
    ic_digits = [int(d) for d in str(ic_last_4)]
    
    # 演算法 1: 出生年份数字之和的个位数
    sum_year = sum(year_digits)
    digit_1 = sum_year % 10
    
    # 演算法 2: IC 前两位相加的个位数
    digit_2 = (ic_digits[0] + ic_digits[1]) % 10
    
    # 演算法 3: IC 后两位相加的个位数
    digit_3 = (ic_digits[2] + ic_digits[3]) % 10
    
    # 演算法 4: 全部数字总和的个位数
    total_sum = sum(year_digits) + sum(ic_digits)
    digit_4 = total_sum % 10
    
    # 组合成 4 位幸运号码
    lucky_number = f"{digit_1}{digit_2}{digit_3}{digit_4}"
    return lucky_number

# 测试您的例子: 1978 和 6009
birth = 1978
ic = "6009"
result = generate_lucky_numbers(birth, ic)
print(f"您的专属幸运号码是: {result}")
