```java
package com.marcelopcx.profile;

import java.time.LocalDate;
import java.time.Period;
import java.util.List;
import org.springframework.stereotype.Component;
import org.springframework.beans.factory.annotation.Autowired;

/**
 * Professional Software Developer & Project Lead
 * Specializing in Backend Systems, Web Scraping, and Mobile Apps.
 */
@Component
public class Marcelo implements Developer {

    private static final LocalDate BIRTH_DATE = LocalDate.of(2003, 3, 8);
    
    @Autowired
    private CurrentProjects activeProjects;

    @Override
    public ProfileInfo getProfile() {
        return ProfileInfo.builder()
            .fullName("Marcelo Perozo")
            .age(Period.between(BIRTH_DATE, LocalDate.now()).getYears())
            .currentRole("Systems Engineering Student & Backend & Mobile Software Developer")
            .location("Maracaibo, Venezuela")
            .build();
    }

    @Override
    public List<String> getLanguages() {
        return List.of("Spanish (Native)", "English");
    }

    @Override
    public Skills getTechStack() {
        return Skills.builder()
            .backend(List.of("Java", "Spring Boot", "Rust", "C++"))
            .frontend(List.of("React Native", "Angular", "HTML5", "CSS3", "JavaScript"))
            .tools(List.of("Git / Gitflow", "Scrum / Agile Boards", "Unix Terminal"))
            .build();
    }

    @Override
    public void displayCurrentFocus() {
        System.out.println("🚀 Current Sprint Focus:");
        
        activeProjects.getFrontend()
            .workingOn("Nook’s Cookbook - Mobile App Frontend");
            
        activeProjects.getBackend()
            .leading("Soy Responsable - Automated Insurance Policy Management System");
            
        activeProjects.getAcademic()
            .finishing("University Research Project & Presentation");
    }

    @Override
    public List<String> getSocials() {
        return List.of(
            "GitHub:   https://github.com/marcelopcx",
            "LinkedIn: https://www.linkedin.com/in/marcelo-pcx",
            "Email:    marceloperozocx@gmail.com"
        );
    }
}
```
