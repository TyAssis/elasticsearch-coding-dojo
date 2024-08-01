Objetivo da Semana:

Implementar estratégias de roteamento eficientes para distribuir dados entre múltiplos índices no Elasticsearch e realizar consultas que abrangem esses índices de forma transparente para o cliente.

Problema Proposto:

A empresa adquiriu duas outras empresas, resultando em dados de candidatos espalhados por diferentes sistemas. O objetivo é integrar esses dados no Elasticsearch, utilizando estratégias de roteamento para otimizar o armazenamento e a recuperação de dados. Além disso, é necessário desenvolver uma solução de consulta que permita aos usuários finais buscar candidatos de qualquer uma das empresas de forma transparente.

Resultado Esperado:

Implementação de uma estrutura de índice eficiente que utilize roteamento customizado para otimizar o desempenho.

Cada empresa tem os dados armazenados em um shard diferente, específico para a empresa, sem misturar dados de empresas diferentes no mesmo shard.

Cada empresa tem os candidatos armazenados em um índice diferente. É possível buscar candidatos de qualquer empresa usando um alias.

Reutilização de consultas da semana anterior. Transforme algumas consultas para consultar dados de uma das empresas ou de qualquer empresa. Para as consultas de qualquer empresa, abstraia a complexidade dos múltiplos índices, permitindo buscas transparentes por candidatos de todas as empresas adquiridas.

Conteúdo Teórico:

Roteamento de Dados no Elasticsearch:

Compreender o conceito de roteamento de dados e como ele pode ser usado para otimizar a performance de leitura e escrita.

Explorar estratégias para roteamento customizado com o objetivo de melhorar a eficiência das consultas.

Trabalhando com Múltiplos Índices:

Aprender como estruturar e organizar dados em múltiplos índices.

Entender o uso de aliases de índice para simplificar consultas em múltiplos índices.

Assets

Essa semana são 3 assets diferentes: company_a_candidates.json, companies_b_candidates.json e companies_c_candidates.json



//company_a_candidates.json
[
    {
        "name": "Mr. Kelly Heaney",
        "title": "Data Analyst",
        "email": "candidato1@example.com",
        "phone": "555-0110",
        "summary": "Efficient project manager",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 9,
        "available_for_work": false,
        "birthdate": "1975-09-23",
        "professional_experience": [
            {
                "company": "Schaden Group",
                "position": "Software Engineer",
                "start_date": "2013-04-22",
                "end_date": "2022-05-10",
                "summary": "If we quantify the interface, we can get to the ASCII circuit through the auxiliary VGA alarm!"
            },
            {
                "company": "Trantow and Sons",
                "position": "Data Analyst",
                "start_date": "2017-11-20",
                "end_date": "2021-05-22",
                "summary": "The SMTP firewall is down, back up the auxiliary card so we can input the SMTP circuit!"
            }
        ],
        "certifications": [
            {
                "name": "virtual Certification",
                "authority": "Kassulke, Roob and Jenkins",
                "year": 2020
            },
            {
                "name": "open-source Certification",
                "authority": "Shields LLC",
                "year": 2016
            },
            {
                "name": "multi-byte Certification",
                "authority": "Hilpert - Franey",
                "year": 2019
            },
            {
                "name": "auxiliary Certification",
                "authority": "Shields and Sons",
                "year": 2018
            }
        ]
    },
    {
        "name": "Kristina Schmeler III",
        "title": "Data Analyst",
        "email": "candidato2@example.com",
        "phone": "555-0111",
        "summary": "Experienced software engineer",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 5,
        "available_for_work": true,
        "birthdate": "1981-01-17",
        "professional_experience": [
            {
                "company": "Mayert - Adams",
                "position": "Software Engineer",
                "start_date": "2014-11-26",
                "end_date": "2022-04-22",
                "summary": "copying the application won't do anything, we need to copy the open-source SQL interface!"
            },
            {
                "company": "Schamberger and Sons",
                "position": "Project Manager",
                "start_date": "2010-05-04",
                "end_date": "2022-04-26",
                "summary": "You can't quantify the monitor without calculating the virtual ASCII driver!"
            }
        ],
        "certifications": [
            {
                "name": "virtual Certification",
                "authority": "Graham Group",
                "year": 2021
            },
            {
                "name": "open-source Certification",
                "authority": "Wilkinson, Keebler and Emard",
                "year": 2016
            }
        ]
    },
    {
        "name": "Leticia Roberts",
        "title": "Data Analyst",
        "email": "candidato3@example.com",
        "phone": "555-0112",
        "summary": "Skilled data analyst",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 5,
        "available_for_work": true,
        "birthdate": "1995-04-21",
        "professional_experience": [
            {
                "company": "Borer, Hartmann and Adams",
                "position": "Data Analyst",
                "start_date": "2010-04-24",
                "end_date": "2021-12-24",
                "summary": "You can't parse the application without hacking the multi-byte PNG protocol!"
            },
            {
                "company": "Leuschke - Douglas",
                "position": "Project Manager",
                "start_date": "2013-04-11",
                "end_date": "2021-10-03",
                "summary": "You can't back up the hard drive without hacking the multi-byte UDP pixel!"
            },
            {
                "company": "Huels LLC",
                "position": "Software Engineer",
                "start_date": "2013-02-08",
                "end_date": "2022-08-24",
                "summary": "You can't navigate the driver without generating the digital TCP driver!"
            }
        ],
        "certifications": [
            {
                "name": "redundant Certification",
                "authority": "Terry - Miller",
                "year": 2017
            },
            {
                "name": "digital Certification",
                "authority": "Olson - Upton",
                "year": 2015
            }
        ]
    },
    {
        "name": "Erica Kozey",
        "title": "Data Analyst",
        "email": "candidato4@example.com",
        "phone": "555-0113",
        "summary": "Efficient project manager",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 2,
        "available_for_work": true,
        "birthdate": "1978-08-15",
        "professional_experience": [
            {
                "company": "Bode - Hermann",
                "position": "Data Analyst",
                "start_date": "2011-07-28",
                "end_date": "2021-03-08",
                "summary": "Use the haptic COM microchip, then you can bypass the auxiliary protocol!"
            }
        ],
        "certifications": [
            {
                "name": "1080p Certification",
                "authority": "Murray - Roberts",
                "year": 2019
            },
            {
                "name": "haptic Certification",
                "authority": "Kozey, Rippin and Bergnaum",
                "year": 2015
            },
            {
                "name": "wireless Certification",
                "authority": "Kuhlman - Barrows",
                "year": 2020
            }
        ]
    },
    {
        "name": "Elvira MacGyver",
        "title": "Software Engineer",
        "email": "candidato5@example.com",
        "phone": "555-0114",
        "summary": "Skilled data analyst",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 3,
        "available_for_work": false,
        "birthdate": "1982-07-06",
        "professional_experience": [
            {
                "company": "Aufderhar, Carter and Lowe",
                "position": "Software Engineer",
                "start_date": "2010-02-04",
                "end_date": "2022-11-08",
                "summary": "overriding the array won't do anything, we need to synthesize the virtual ASCII alarm!"
            },
            {
                "company": "Ritchie - O'Kon",
                "position": "Software Engineer",
                "start_date": "2016-11-28",
                "end_date": "2019-02-20",
                "summary": "Use the redundant SAS system, then you can copy the digital application!"
            },
            {
                "company": "Nicolas, Bayer and Lang",
                "position": "Project Manager",
                "start_date": "2015-01-28",
                "end_date": "2019-06-16",
                "summary": "Try to program the ADP transmitter, maybe it will override the virtual matrix!"
            }
        ],
        "certifications": [
            {
                "name": "bluetooth Certification",
                "authority": "Nader, Steuber and Ebert",
                "year": 2016
            },
            {
                "name": "online Certification",
                "authority": "Watsica - Rogahn",
                "year": 2021
            }
        ]
    },
    {
        "name": "Max Homenick",
        "title": "Project Manager",
        "email": "candidato6@example.com",
        "phone": "555-0115",
        "summary": "Experienced software engineer",
        "languages": [
            "German"
        ],
        "years_of_experience": 5,
        "available_for_work": true,
        "birthdate": "1983-03-27",
        "professional_experience": [
            {
                "company": "Metz, Stiedemann and Braun",
                "position": "Software Engineer",
                "start_date": "2012-03-11",
                "end_date": "2021-10-05",
                "summary": "hacking the sensor won't do anything, we need to program the open-source SSD port!"
            },
            {
                "company": "Windler LLC",
                "position": "Project Manager",
                "start_date": "2018-12-20",
                "end_date": "2019-07-22",
                "summary": "Use the cross-platform PNG bus, then you can back up the auxiliary panel!"
            }
        ],
        "certifications": [
            {
                "name": "wireless Certification",
                "authority": "Ryan, Will and Towne",
                "year": 2016
            },
            {
                "name": "open-source Certification",
                "authority": "Rogahn - Larkin",
                "year": 2017
            },
            {
                "name": "digital Certification",
                "authority": "Macejkovic - Altenwerth",
                "year": 2016
            }
        ]
    },
    {
        "name": "Freddie Bins",
        "title": "Project Manager",
        "email": "candidato7@example.com",
        "phone": "555-0116",
        "summary": "Skilled data analyst",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 4,
        "available_for_work": false,
        "birthdate": "1995-01-09",
        "professional_experience": [
            {
                "company": "Gibson - Boyle",
                "position": "Data Analyst",
                "start_date": "2015-01-19",
                "end_date": "2021-07-21",
                "summary": "You can't override the card without backing up the mobile DRAM port!"
            },
            {
                "company": "Aufderhar Group",
                "position": "Data Analyst",
                "start_date": "2015-07-12",
                "end_date": "2019-06-16",
                "summary": "You can't input the bandwidth without generating the wireless JBOD program!"
            },
            {
                "company": "Goodwin, Von and Haag",
                "position": "Software Engineer",
                "start_date": "2018-05-22",
                "end_date": "2020-10-20",
                "summary": "You can't override the driver without bypassing the bluetooth SSL sensor!"
            }
        ],
        "certifications": [
            {
                "name": "optical Certification",
                "authority": "Keeling - Torphy",
                "year": 2020
            }
        ]
    },
    {
        "name": "Rex West",
        "title": "Project Manager",
        "email": "candidato8@example.com",
        "phone": "555-0117",
        "summary": "Efficient project manager",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 10,
        "available_for_work": false,
        "birthdate": "1998-06-12",
        "professional_experience": [
            {
                "company": "Nader - Von",
                "position": "Data Analyst",
                "start_date": "2011-03-16",
                "end_date": "2021-12-19",
                "summary": "Try to transmit the DRAM hard drive, maybe it will generate the mobile program!"
            }
        ],
        "certifications": [
            {
                "name": "open-source Certification",
                "authority": "Pouros, Lynch and Veum",
                "year": 2020
            },
            {
                "name": "auxiliary Certification",
                "authority": "Haley Group",
                "year": 2020
            },
            {
                "name": "mobile Certification",
                "authority": "Cronin and Sons",
                "year": 2018
            },
            {
                "name": "back-end Certification",
                "authority": "Kovacek, Schinner and Walter",
                "year": 2018
            }
        ]
    },
    {
        "name": "Lillian Ziemann",
        "title": "Data Analyst",
        "email": "candidato9@example.com",
        "phone": "555-0118",
        "summary": "Skilled data analyst",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 7,
        "available_for_work": false,
        "birthdate": "1978-09-05",
        "professional_experience": [
            {
                "company": "Nolan, Jones and Littel",
                "position": "Project Manager",
                "start_date": "2015-12-06",
                "end_date": "2020-02-14",
                "summary": "navigating the bandwidth won't do anything, we need to transmit the wireless THX capacitor!"
            },
            {
                "company": "Schimmel, Luettgen and Harvey",
                "position": "Software Engineer",
                "start_date": "2014-02-04",
                "end_date": "2019-07-15",
                "summary": "Try to copy the EXE sensor, maybe it will generate the 1080p card!"
            },
            {
                "company": "Ferry - Torphy",
                "position": "Project Manager",
                "start_date": "2018-07-11",
                "end_date": "2019-06-15",
                "summary": "Use the auxiliary COM system, then you can synthesize the haptic pixel!"
            }
        ],
        "certifications": [
            {
                "name": "bluetooth Certification",
                "authority": "Johns - Mueller",
                "year": 2016
            },
            {
                "name": "cross-platform Certification",
                "authority": "Donnelly - Lind",
                "year": 2019
            }
        ]
    },
    {
        "name": "Wendell Douglas",
        "title": "Software Engineer",
        "email": "candidato10@example.com",
        "phone": "555-0119",
        "summary": "Experienced software engineer",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 7,
        "available_for_work": false,
        "birthdate": "1975-09-08",
        "professional_experience": [
            {
                "company": "Zboncak - Reichel",
                "position": "Software Engineer",
                "start_date": "2010-08-02",
                "end_date": "2022-10-09",
                "summary": "Use the auxiliary SMTP system, then you can parse the wireless port!"
            },
            {
                "company": "DuBuque LLC",
                "position": "Project Manager",
                "start_date": "2010-04-10",
                "end_date": "2020-12-19",
                "summary": "If we navigate the protocol, we can get to the API card through the mobile USB monitor!"
            }
        ],
        "certifications": [
            {
                "name": "back-end Certification",
                "authority": "Boehm Inc",
                "year": 2017
            },
            {
                "name": "cross-platform Certification",
                "authority": "Legros - Blanda",
                "year": 2017
            },
            {
                "name": "auxiliary Certification",
                "authority": "Pfannerstill and Sons",
                "year": 2017
            },
            {
                "name": "bluetooth Certification",
                "authority": "Kuhic Inc",
                "year": 2016
            }
        ]
    }
]


//company_b_candidates.json
[
    {
        "name": "Eula Purdy",
        "title": "Project Manager",
        "email": "candidato1@example.com",
        "phone": "555-0110",
        "summary": "Skilled data analyst",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 6,
        "available_for_work": false,
        "birthdate": "1991-09-20",
        "professional_experience": [
            {
                "company": "Hermiston - Schuster",
                "position": "Project Manager",
                "start_date": "2015-11-13",
                "end_date": "2020-06-05",
                "summary": "You can't override the capacitor without backing up the haptic SDD port!"
            },
            {
                "company": "Frami, Douglas and Hamill",
                "position": "Project Manager",
                "start_date": "2010-05-25",
                "end_date": "2021-09-02",
                "summary": "If we parse the bandwidth, we can get to the IB firewall through the multi-byte COM panel!"
            }
        ],
        "certifications": [
            {
                "name": "open-source Certification",
                "authority": "Stroman, Reichel and Schamberger",
                "year": 2018
            },
            {
                "name": "virtual Certification",
                "authority": "Reinger Inc",
                "year": 2020
            },
            {
                "name": "haptic Certification",
                "authority": "Herman - Lebsack",
                "year": 2021
            },
            {
                "name": "digital Certification",
                "authority": "Yundt, Muller and Collier",
                "year": 2021
            }
        ]
    },
    {
        "name": "Jim Corwin",
        "title": "Project Manager",
        "email": "candidato2@example.com",
        "phone": "555-0111",
        "summary": "Experienced software engineer",
        "languages": [
            "German"
        ],
        "years_of_experience": 4,
        "available_for_work": false,
        "birthdate": "1990-02-26",
        "professional_experience": [
            {
                "company": "O'Hara, Stroman and Casper",
                "position": "Data Analyst",
                "start_date": "2016-01-07",
                "end_date": "2022-04-26",
                "summary": "The RSS pixel is down, transmit the haptic driver so we can override the HEX protocol!"
            }
        ],
        "certifications": [
            {
                "name": "solid state Certification",
                "authority": "Jast - Ortiz",
                "year": 2021
            }
        ]
    },
    {
        "name": "Terry Mante",
        "title": "Software Engineer",
        "email": "candidato3@example.com",
        "phone": "555-0112",
        "summary": "Efficient project manager",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 6,
        "available_for_work": true,
        "birthdate": "1986-08-12",
        "professional_experience": [
            {
                "company": "Emard Group",
                "position": "Project Manager",
                "start_date": "2018-08-03",
                "end_date": "2019-11-18",
                "summary": "I'll calculate the redundant UDP firewall, that should bandwidth the TCP circuit!"
            }
        ],
        "certifications": [
            {
                "name": "open-source Certification",
                "authority": "Schmidt - Pfeffer",
                "year": 2022
            },
            {
                "name": "open-source Certification",
                "authority": "Ledner - West",
                "year": 2017
            },
            {
                "name": "auxiliary Certification",
                "authority": "Kris and Sons",
                "year": 2018
            },
            {
                "name": "bluetooth Certification",
                "authority": "Huels, Green and Little",
                "year": 2020
            }
        ]
    },
    {
        "name": "Eduardo Block",
        "title": "Project Manager",
        "email": "candidato4@example.com",
        "phone": "555-0113",
        "summary": "Efficient project manager",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 2,
        "available_for_work": false,
        "birthdate": "1973-10-10",
        "professional_experience": [
            {
                "company": "Braun and Sons",
                "position": "Project Manager",
                "start_date": "2010-12-24",
                "end_date": "2021-09-24",
                "summary": "Use the cross-platform SMS system, then you can quantify the haptic capacitor!"
            }
        ],
        "certifications": [
            {
                "name": "bluetooth Certification",
                "authority": "Schinner, Schinner and Weber",
                "year": 2020
            }
        ]
    },
    {
        "name": "Nicholas Huel",
        "title": "Project Manager",
        "email": "candidato5@example.com",
        "phone": "555-0114",
        "summary": "Efficient project manager",
        "languages": [
            "German"
        ],
        "years_of_experience": 0,
        "available_for_work": true,
        "birthdate": "1996-06-18",
        "professional_experience": [
            {
                "company": "Casper, Wunsch and Fisher",
                "position": "Data Analyst",
                "start_date": "2014-06-04",
                "end_date": "2021-12-02",
                "summary": "parsing the panel won't do anything, we need to copy the virtual JSON panel!"
            }
        ],
        "certifications": [
            {
                "name": "solid state Certification",
                "authority": "Harris - Reichert",
                "year": 2015
            }
        ]
    },
    {
        "name": "Salvatore Schiller",
        "title": "Data Analyst",
        "email": "candidato6@example.com",
        "phone": "555-0115",
        "summary": "Experienced software engineer",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 4,
        "available_for_work": true,
        "birthdate": "1982-11-20",
        "professional_experience": [
            {
                "company": "Koss - Durgan",
                "position": "Software Engineer",
                "start_date": "2015-12-26",
                "end_date": "2021-01-16",
                "summary": "You can't transmit the circuit without transmitting the multi-byte PNG panel!"
            },
            {
                "company": "Connelly, Ondricka and Schowalter",
                "position": "Data Analyst",
                "start_date": "2014-09-26",
                "end_date": "2019-04-13",
                "summary": "You can't transmit the alarm without generating the bluetooth HEX sensor!"
            }
        ],
        "certifications": [
            {
                "name": "auxiliary Certification",
                "authority": "Franecki Group",
                "year": 2015
            },
            {
                "name": "mobile Certification",
                "authority": "Smith, Hamill and Stamm",
                "year": 2022
            },
            {
                "name": "virtual Certification",
                "authority": "D'Amore - Heaney",
                "year": 2020
            },
            {
                "name": "optical Certification",
                "authority": "Ruecker - Trantow",
                "year": 2018
            }
        ]
    },
    {
        "name": "Karen Reynolds",
        "title": "Software Engineer",
        "email": "candidato7@example.com",
        "phone": "555-0116",
        "summary": "Skilled data analyst",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 0,
        "available_for_work": false,
        "birthdate": "1975-08-19",
        "professional_experience": [
            {
                "company": "Borer, Nikolaus and Ledner",
                "position": "Project Manager",
                "start_date": "2016-10-10",
                "end_date": "2019-10-08",
                "summary": "If we override the program, we can get to the VGA driver through the cross-platform API capacitor!"
            },
            {
                "company": "Balistreri, Trantow and Zulauf",
                "position": "Project Manager",
                "start_date": "2017-11-01",
                "end_date": "2020-01-11",
                "summary": "We need to bypass the optical OCR microchip!"
            },
            {
                "company": "Koelpin - Boyle",
                "position": "Project Manager",
                "start_date": "2013-04-13",
                "end_date": "2022-02-07",
                "summary": "I'll compress the redundant SSL driver, that should protocol the GB firewall!"
            }
        ],
        "certifications": [
            {
                "name": "back-end Certification",
                "authority": "Kutch - Jacobson",
                "year": 2021
            },
            {
                "name": "primary Certification",
                "authority": "Emmerich LLC",
                "year": 2020
            }
        ]
    },
    {
        "name": "Delia Ruecker Jr.",
        "title": "Software Engineer",
        "email": "candidato8@example.com",
        "phone": "555-0117",
        "summary": "Efficient project manager",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 10,
        "available_for_work": false,
        "birthdate": "1990-09-26",
        "professional_experience": [
            {
                "company": "Kshlerin - Emard",
                "position": "Software Engineer",
                "start_date": "2018-03-19",
                "end_date": "2020-05-09",
                "summary": "hacking the interface won't do anything, we need to quantify the haptic RSS capacitor!"
            },
            {
                "company": "Bruen, Mitchell and Kuvalis",
                "position": "Data Analyst",
                "start_date": "2018-02-11",
                "end_date": "2021-02-21",
                "summary": "If we program the protocol, we can get to the FTP transmitter through the solid state SSD firewall!"
            },
            {
                "company": "Langworth LLC",
                "position": "Data Analyst",
                "start_date": "2018-07-18",
                "end_date": "2019-03-03",
                "summary": "Try to transmit the AI array, maybe it will back up the solid state feed!"
            }
        ],
        "certifications": [
            {
                "name": "primary Certification",
                "authority": "Cummerata LLC",
                "year": 2018
            },
            {
                "name": "neural Certification",
                "authority": "Marquardt Inc",
                "year": 2019
            }
        ]
    },
    {
        "name": "Elizabeth Kautzer",
        "title": "Data Analyst",
        "email": "candidato9@example.com",
        "phone": "555-0118",
        "summary": "Efficient project manager",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 5,
        "available_for_work": false,
        "birthdate": "1991-03-12",
        "professional_experience": [
            {
                "company": "Shields - Reinger",
                "position": "Project Manager",
                "start_date": "2012-10-17",
                "end_date": "2020-09-06",
                "summary": "The IB transmitter is down, index the bluetooth matrix so we can back up the HDD capacitor!"
            },
            {
                "company": "Wisoky, Altenwerth and Kerluke",
                "position": "Data Analyst",
                "start_date": "2012-10-03",
                "end_date": "2020-01-18",
                "summary": "If we compress the system, we can get to the PCI firewall through the optical XSS circuit!"
            }
        ],
        "certifications": [
            {
                "name": "online Certification",
                "authority": "Waters, Ullrich and Will",
                "year": 2018
            },
            {
                "name": "multi-byte Certification",
                "authority": "Brekke, Shanahan and Stoltenberg",
                "year": 2021
            },
            {
                "name": "auxiliary Certification",
                "authority": "Jast, MacGyver and Ritchie",
                "year": 2021
            }
        ]
    },
    {
        "name": "Marion Harvey",
        "title": "Software Engineer",
        "email": "candidato10@example.com",
        "phone": "555-0119",
        "summary": "Efficient project manager",
        "languages": [
            "German"
        ],
        "years_of_experience": 5,
        "available_for_work": false,
        "birthdate": "2000-07-01",
        "professional_experience": [
            {
                "company": "Renner, Harber and Runolfsdottir",
                "position": "Software Engineer",
                "start_date": "2017-05-15",
                "end_date": "2022-10-23",
                "summary": "Try to program the UDP application, maybe it will hack the solid state transmitter!"
            }
        ],
        "certifications": [
            {
                "name": "cross-platform Certification",
                "authority": "Fadel, Wintheiser and Crona",
                "year": 2020
            }
        ]
    }
]


//company_c_candidates.json
[
    {
        "name": "Nick Schmeler",
        "title": "Project Manager",
        "email": "candidato1@example.com",
        "phone": "555-0110",
        "summary": "Experienced software engineer",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 7,
        "available_for_work": true,
        "birthdate": "1977-11-26",
        "professional_experience": [
            {
                "company": "Flatley - Hansen",
                "position": "Project Manager",
                "start_date": "2017-10-28",
                "end_date": "2019-10-20",
                "summary": "Use the cross-platform PCI port, then you can program the cross-platform firewall!"
            },
            {
                "company": "Haley, Mohr and DuBuque",
                "position": "Data Analyst",
                "start_date": "2016-01-07",
                "end_date": "2019-03-12",
                "summary": "I'll synthesize the primary UDP alarm, that should application the SQL card!"
            }
        ],
        "certifications": [
            {
                "name": "neural Certification",
                "authority": "Hayes - Schultz",
                "year": 2020
            }
        ]
    },
    {
        "name": "Rufus Heller",
        "title": "Software Engineer",
        "email": "candidato2@example.com",
        "phone": "555-0111",
        "summary": "Experienced software engineer",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 0,
        "available_for_work": true,
        "birthdate": "1999-05-17",
        "professional_experience": [
            {
                "company": "Ortiz, Schowalter and Runte",
                "position": "Project Manager",
                "start_date": "2017-01-17",
                "end_date": "2021-04-02",
                "summary": "Use the auxiliary DNS pixel, then you can input the solid state matrix!"
            }
        ],
        "certifications": [
            {
                "name": "haptic Certification",
                "authority": "Mann Group",
                "year": 2019
            }
        ]
    },
    {
        "name": "Dr. Esther Hills",
        "title": "Data Analyst",
        "email": "candidato3@example.com",
        "phone": "555-0112",
        "summary": "Experienced software engineer",
        "languages": [
            "German"
        ],
        "years_of_experience": 0,
        "available_for_work": false,
        "birthdate": "1990-01-16",
        "professional_experience": [
            {
                "company": "Lang, Barrows and Davis",
                "position": "Project Manager",
                "start_date": "2011-05-04",
                "end_date": "2020-08-10",
                "summary": "overriding the system won't do anything, we need to transmit the haptic SAS alarm!"
            },
            {
                "company": "Erdman, Dicki and Lemke",
                "position": "Project Manager",
                "start_date": "2016-12-04",
                "end_date": "2021-09-21",
                "summary": "The ADP capacitor is down, reboot the solid state system so we can copy the AI array!"
            }
        ],
        "certifications": [
            {
                "name": "redundant Certification",
                "authority": "Langworth - Block",
                "year": 2020
            }
        ]
    },
    {
        "name": "Bradley Jacobi",
        "title": "Project Manager",
        "email": "candidato4@example.com",
        "phone": "555-0113",
        "summary": "Experienced software engineer",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 8,
        "available_for_work": true,
        "birthdate": "1998-07-07",
        "professional_experience": [
            {
                "company": "Renner - Schowalter",
                "position": "Project Manager",
                "start_date": "2017-11-23",
                "end_date": "2021-06-18",
                "summary": "Use the wireless SMTP panel, then you can connect the virtual firewall!"
            },
            {
                "company": "Shields - Bradtke",
                "position": "Project Manager",
                "start_date": "2014-04-04",
                "end_date": "2021-01-15",
                "summary": "You can't program the system without calculating the auxiliary FTP pixel!"
            }
        ],
        "certifications": [
            {
                "name": "multi-byte Certification",
                "authority": "Lueilwitz Inc",
                "year": 2015
            }
        ]
    },
    {
        "name": "Jackie Schroeder",
        "title": "Software Engineer",
        "email": "candidato5@example.com",
        "phone": "555-0114",
        "summary": "Skilled data analyst",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 8,
        "available_for_work": true,
        "birthdate": "1985-08-07",
        "professional_experience": [
            {
                "company": "Sporer - Prohaska",
                "position": "Data Analyst",
                "start_date": "2014-11-07",
                "end_date": "2022-06-10",
                "summary": "The API application is down, connect the haptic pixel so we can synthesize the XSS alarm!"
            },
            {
                "company": "Harvey Group",
                "position": "Project Manager",
                "start_date": "2017-04-05",
                "end_date": "2022-08-05",
                "summary": "programming the transmitter won't do anything, we need to index the virtual USB protocol!"
            },
            {
                "company": "Nicolas, Beer and Lebsack",
                "position": "Data Analyst",
                "start_date": "2011-06-24",
                "end_date": "2019-09-01",
                "summary": "You can't quantify the array without generating the mobile SQL application!"
            }
        ],
        "certifications": [
            {
                "name": "haptic Certification",
                "authority": "Mayert, Rau and Quitzon",
                "year": 2020
            },
            {
                "name": "cross-platform Certification",
                "authority": "Jacobi and Sons",
                "year": 2019
            }
        ]
    },
    {
        "name": "Darrel Volkman",
        "title": "Software Engineer",
        "email": "candidato6@example.com",
        "phone": "555-0115",
        "summary": "Experienced software engineer",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 2,
        "available_for_work": false,
        "birthdate": "1989-06-23",
        "professional_experience": [
            {
                "company": "Prohaska Inc",
                "position": "Project Manager",
                "start_date": "2015-12-27",
                "end_date": "2021-05-21",
                "summary": "parsing the system won't do anything, we need to input the haptic SCSI interface!"
            },
            {
                "company": "Gleason - Schowalter",
                "position": "Project Manager",
                "start_date": "2010-11-23",
                "end_date": "2021-02-10",
                "summary": "If we generate the hard drive, we can get to the AGP card through the open-source VGA sensor!"
            },
            {
                "company": "Cartwright Inc",
                "position": "Project Manager",
                "start_date": "2015-03-04",
                "end_date": "2021-04-01",
                "summary": "We need to parse the digital SDD application!"
            }
        ],
        "certifications": [
            {
                "name": "haptic Certification",
                "authority": "Kunde, Gerhold and Hermiston",
                "year": 2015
            },
            {
                "name": "wireless Certification",
                "authority": "Oberbrunner - Murphy",
                "year": 2020
            }
        ]
    },
    {
        "name": "Danielle Walsh DVM",
        "title": "Software Engineer",
        "email": "candidato7@example.com",
        "phone": "555-0116",
        "summary": "Experienced software engineer",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 4,
        "available_for_work": true,
        "birthdate": "1975-12-17",
        "professional_experience": [
            {
                "company": "Kuhlman - Hamill",
                "position": "Software Engineer",
                "start_date": "2014-01-07",
                "end_date": "2019-10-24",
                "summary": "I'll program the optical SQL protocol, that should bandwidth the HTTP pixel!"
            }
        ],
        "certifications": [
            {
                "name": "multi-byte Certification",
                "authority": "Schneider - Boyer",
                "year": 2017
            },
            {
                "name": "haptic Certification",
                "authority": "Lehner - Huels",
                "year": 2017
            },
            {
                "name": "digital Certification",
                "authority": "Kautzer - Bradtke",
                "year": 2016
            },
            {
                "name": "primary Certification",
                "authority": "Kuhn and Sons",
                "year": 2016
            }
        ]
    },
    {
        "name": "Jennie Gorczany V",
        "title": "Project Manager",
        "email": "candidato8@example.com",
        "phone": "555-0117",
        "summary": "Efficient project manager",
        "languages": [
            "Portuguese",
            "French"
        ],
        "years_of_experience": 6,
        "available_for_work": false,
        "birthdate": "1977-03-17",
        "professional_experience": [
            {
                "company": "Denesik - MacGyver",
                "position": "Data Analyst",
                "start_date": "2010-11-02",
                "end_date": "2022-03-23",
                "summary": "transmitting the circuit won't do anything, we need to back up the multi-byte SSD application!"
            }
        ],
        "certifications": [
            {
                "name": "solid state Certification",
                "authority": "Larson LLC",
                "year": 2015
            },
            {
                "name": "1080p Certification",
                "authority": "Marquardt, Heller and Gerlach",
                "year": 2018
            },
            {
                "name": "open-source Certification",
                "authority": "Mertz - Nader",
                "year": 2021
            }
        ]
    },
    {
        "name": "Erick Tromp",
        "title": "Project Manager",
        "email": "candidato9@example.com",
        "phone": "555-0118",
        "summary": "Efficient project manager",
        "languages": [
            "English",
            "Spanish"
        ],
        "years_of_experience": 7,
        "available_for_work": true,
        "birthdate": "1994-03-09",
        "professional_experience": [
            {
                "company": "Kozey, Romaguera and Hamill",
                "position": "Data Analyst",
                "start_date": "2014-11-06",
                "end_date": "2020-10-20",
                "summary": "The ASCII feed is down, connect the bluetooth capacitor so we can copy the PCI monitor!"
            },
            {
                "company": "McCullough - Ankunding",
                "position": "Data Analyst",
                "start_date": "2014-08-28",
                "end_date": "2021-08-03",
                "summary": "The DRAM microchip is down, hack the 1080p microchip so we can program the XML alarm!"
            },
            {
                "company": "Abshire, Bechtelar and Hilpert",
                "position": "Software Engineer",
                "start_date": "2012-07-04",
                "end_date": "2019-07-09",
                "summary": "I'll bypass the virtual SMS bandwidth, that should alarm the AGP application!"
            }
        ],
        "certifications": [
            {
                "name": "back-end Certification",
                "authority": "Bartell LLC",
                "year": 2016
            },
            {
                "name": "wireless Certification",
                "authority": "Ankunding Group",
                "year": 2022
            },
            {
                "name": "optical Certification",
                "authority": "Jacobson, Harris and Kemmer",
                "year": 2017
            },
            {
                "name": "neural Certification",
                "authority": "Friesen - Gusikowski",
                "year": 2016
            }
        ]
    },
    {
        "name": "Chelsea Greenfelder",
        "title": "Software Engineer",
        "email": "candidato10@example.com",
        "phone": "555-0119",
        "summary": "Skilled data analyst",
        "languages": [
            "German"
        ],
        "years_of_experience": 0,
        "available_for_work": true,
        "birthdate": "1978-02-21",
        "professional_experience": [
            {
                "company": "Walsh, Keebler and Barrows",
                "position": "Project Manager",
                "start_date": "2017-05-13",
                "end_date": "2022-12-09",
                "summary": "Use the multi-byte RSS feed, then you can hack the online card!"
            },
            {
                "company": "Osinski - Lynch",
                "position": "Project Manager",
                "start_date": "2017-04-03",
                "end_date": "2021-11-15",
                "summary": "Use the mobile JBOD pixel, then you can copy the auxiliary port!"
            }
        ],
        "certifications": [
            {
                "name": "optical Certification",
                "authority": "Williamson - Turcotte",
                "year": 2017
            },
            {
                "name": "wireless Certification",
                "authority": "Schmitt LLC",
                "year": 2022
            },
            {
                "name": "primary Certification",
                "authority": "Price Group",
                "year": 2020
            }
        ]
    }
]