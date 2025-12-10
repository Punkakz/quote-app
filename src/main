package com.akhtar.quotes;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.client.RestTemplate;

import java.util.HashMap;
import java.util.Map;

@RestController
public class QuoteController {

    @GetMapping("/quote")
    public Map<String, String> getQuote() {

        RestTemplate rest = new RestTemplate();

        // Get random quote
        Map quote = rest.getForObject("https://api.quotable.io/random", Map.class);

        String content = quote.get("content").toString();
        String author = quote.get("author").toString();

        // Image generator
        String img = "https://source.unsplash.com/600x400/?portrait," + author;

        Map<String, String> response = new HashMap<>();
        response.put("quote", content);
        response.put("author", author);
        response.put("image", img);

        return response;
    }
}
