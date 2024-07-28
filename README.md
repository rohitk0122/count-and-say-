# count-and-say-
class Solution {
    public String countAndSay(int n) {
        if (n <= 0) {
            return "";
        }
        
        String result = "1";
        for (int i = 1; i < n; i++) {
            result = getNextSequence(result);
        }
        
        return result;
    }

    private String getNextSequence(String s) {
        StringBuilder sb = new StringBuilder();
        int count = 1;
        
        for (int i = 1; i < s.length(); i++) {
            if (s.charAt(i) == s.charAt(i - 1)) {
                count++;
            } else {
                sb.append(count).append(s.charAt(i - 1));
                count = 1;
            }
        }
        
        sb.append(count).append(s.charAt(s.length() - 1));
        return sb.toString();
    }
}
