        while (rest != 0){
            // we use long to store c,because integer maybe overflow.
            long c = (rest * 10) / denominator;
            // when rest is in the map (have the same rest), code will be in a loop.so we break this loop.
            if (map.get(rest) != null){
                ans.insert(map.get(rest) + 1,"(");
                ans.append(")");
                break;
            }
            map.put(rest,ans.length() - 1);
            ans.append(Math.abs(c));
            rest = (rest * 10) % denominator;
        }
