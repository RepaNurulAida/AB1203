#include <iostream>
#include <string>
#include <map>

std::string nextday(const std::string& current_day) {
    std::map<std::string, std::string> days = {
        {"senin", "selasa"}, {"selasa", "rabu"}, {"rabu", "kamis"},
        {"kamis", "jumat"}, {"jumat", "sabtu"}, {"sabtu", "minggu"}, {"minggu", "senin"}
    };
    auto it = days.find(current_day);
    if (it != days.end()) {
        return it->second;
    }
    std::cout << "Hari yang tidak valid: " << current_day << std::endl;
    return "";
}

int main() {
    std::string today = "rabu";
    std::string tomorrow = nextday(today);
    if (!tomorrow.empty()) {
        std::cout << "Besok adalah: " << tomorrow << std::endl;
    }
    return 0;
}
