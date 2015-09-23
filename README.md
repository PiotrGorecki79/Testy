# Testy
to jest moje pierwsze repozytorium
ciekawe, co z tego wyjdzie

*** Test Cases ***
Logowanie
    [Tags]    do_testu_2
    Set Window Size    1680    1050
    Location Should Be    http://pracodawca.pracuj.pl/
    Wait Until Page Contains    Szukasz pracownika?
    Wait Until Page Contains    Zamów ogłoszenie i znajdź go na Pracuj.pl
    Wait Until Page Contains Element    //div[@class='header-logo']//h1[contains(.,'Strefa dla pracodawców')]
    Wait Until Page Contains Element    //div[@class='header-logo']//h2[contains(.,'Tu zamówisz i opublikujesz ogłoszenie na Pracuj.pl')]
    Page Should Contain Element    //div[@class='header-konto']//a[@href='https://sklep.pracuj.pl/Account/Login.aspx'] [contains(.,'KONTO PRACODAWCY')]
    Click Element    //div[@class='header-konto']//a[@href='https://sklep.pracuj.pl/Account/Login.aspx'] [contains(.,'KONTO PRACODAWCY')]
    Wait Until Page Contains    Dostęp do Konta Pracodawcy
    Location Should Be    https://sklep.pracuj.pl/Account/Login.aspx
    Page Should Contain Element    //div[@class='rejestracjaLogowanie section-item']/h1[contains(.,'Dostęp do Konta Pracodawcy')]
    Page Should Contain Element    //input[@id='ctl00_DefaultContent_tbxLogin']
    Page Should Contain Element    //input[@id='ctl00_DefaultContent_tbxPassword']
    Page Should Contain Element    //input[@class='btn-red btn-large']
    Input Text    //input[@id='ctl00_DefaultContent_tbxLogin']    ${login}
    Input Password    //input[@id='ctl00_DefaultContent_tbxPassword']    ${haslo}
    Click Element    //input[@class='btn-red btn-large']
    Wait Until Page Contains    Firma Testowa Adam Omikron
    Location Should Be    https://sklep.pracuj.pl/Offers/Dashboard.aspx
    Page Should Contain    Witaj
    Page Should Contain    Adam Omikron
    Page Should Contain    Firma Testowa Adam Omikron
    Page Should Contain Element    //span[@id='ctl00_lUserName'][contains(.,'Adam Omikron')]
    Page Should Contain Element    //span[@id='ctl00_lCompanyFullName'][contains(.,'Firma Testowa Adam Omikron')]
    Page Should Contain Element    //a[@id='ctl00_LoginStatus1'][contains(.,'Wyloguj')]
    Click Element    //a[@id='ctl00_LoginStatus1'][contains(.,'Wyloguj')]
