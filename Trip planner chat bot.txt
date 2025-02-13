import spacy

class TripPlanner:
    def __init__(self):
        print("Hey, This is an Trip planner chatbot! How can I assist you?")
        self.destinations = {
            "paris": {
                "attractions": ["Eiffel Tower", "Louvre Museum", "Notre-Dame Cathedral", "Seine River Cruise", "Montmartre", "Champs-Élysées", "Musée d'Orsay", "Sacré-Cœur Basilica", "Arc de Triomphe"],
                "weather": "Mild and rainy",
                "best_time_to_visit": "Spring or Fall",
                "boarding": "https://parisjetaime.com/eng/practical-paris/where-to-sleep-in-paris-i104",
                 "travel_facilities": {
            "airports": ["Charles de Gaulle Airport", "Orly Airport"],
            "train_stations": ["Gare du Nord", "Gare de Lyon"],
            "metro_stations": ["Champs-Élysées - Clemenceau", "Louvre - Rivoli"],
            "bus_stations": ["Gare Montparnasse", "Porte Maillot"],
            "car_rental": "available",
            "taxis": "available"
        }
            },
            "new york": {
                "attractions": ["Statue of Liberty", "Central Park", "Times Square", "Empire State Building", "Brooklyn Bridge", "Metropolitan Museum of Art", "The High Line", "One World Trade Center", "Broadway", "5th Avenue"],
                "weather": "Varied",
                "best_time_to_visit": "Anytime",
                "boarding": "https://www.wotif.com/New-York-Hotels.d178293.Travel-Guide-Hotels",
                "travel_facilities": {
            "airports": ["John F. Kennedy International Airport", "LaGuardia Airport"],
            "train_stations": ["Penn Station", "Grand Central Terminal"],
            "subway_stations": ["Times Square - 42nd Street", "Grand Central - 42nd Street"],
            "bus_stations": ["Port Authority Bus Terminal", "Penn Station"],
            "car_rental": "available",
            "taxis": "available"
        }
            },
            "delhi": {
                "attractions": ["Red Fort", "India Gate", "Qutub Minar", "Lotus Temple", "Humayun's Tomb", "Akshardham Temple", "Jama Masjid", "Raj Ghat", "Rashtrapati Bhavan", "Chandni Chowk"],
                "weather": "Hot summers and cool winters",
                "best_time_to_visit": "October to March",
                "boarding": "https://www.goibibo.com/hotels/hotels-in-delhi-ct",
                "travel_facilities": {
            "airports": ["Indira Gandhi International Airport"],
            "train_stations": ["New Delhi Railway Station", "Old Delhi Railway Station"],
            "metro_stations": ["Rajiv Chowk", "Kashmiri Gate"],
            "bus_stations": ["Kashmere Gate ISBT", "Anand Vihar ISBT"],
            "car_rental": "available",
            "taxis": "available"
                }

            },
            "mumbai": {
                "attractions": ["Gateway of India", "Marine Drive", "Chhatrapati Shivaji Maharaj Terminus", "Elephanta Caves", "Siddhivinayak Temple", "Haji Ali Dargah", "Juhu Beach", "Colaba Causeway", "Hanging Gardens", "Chor Bazaar"],
                "weather": "Humid and moderate",
                "best_time_to_visit": "November to February",
                "boarding": "https://www.goibibo.com/hotels/",
                "travel_facilities": {
            "airports": ["Chhatrapati Shivaji Maharaj International Airport"],
            "train_stations": ["Chhatrapati Shivaji Maharaj Terminus", "Mumbai Central"],
            "metro_stations": ["Andheri", "Ghatkopar"],
            "bus_stations": ["Dadar Bus Station", "Borivali Bus Depot"],
            "car_rental": "available",
            "taxis": "available"
                }
            },
            "goa": {
                "attractions": ["Baga Beach", "Calangute Beach", "Anjuna Beach", "Fort Aguada", "Basilica of Bom Jesus", "Se Cathedral", "Dudhsagar Falls", "Chapora Fort", "Palolem Beach", "Dona Paula"],
                "weather": "Tropical climate",
                "best_time_to_visit": "November to March",
                "boarding": "https://www.booking.com/city/in/goa.en-gb.html",
                "travel_facilities": {
            "airports": ["Goa International Airport (Dabolim Airport)"],
            "train_stations": ["Madgaon Railway Station", "Thivim Railway Station"],
            "bus_stations": ["Mapusa Bus Stand", "Panjim Bus Stand"],
            "car_rental": "available",
            "taxis": "available"
                }

            },
            "london": {
                "attractions": ["British Museum", "Tower of London", "Buckingham Palace", "London Eye", "Big Ben", "Westminster Abbey", "Tate Modern", "The Shard", "Hyde Park", "St. Paul's Cathedral"],
                "weather": "Mild and wet",
                "best_time_to_visit": "March to May",
                "boarding": "https://www.booking.com/city/gb/london.en-gb.html",
                 "travel_facilities": {
            "airports": ["Heathrow Airport", "Gatwick Airport"],
            "train_stations": ["London Paddington", "London King's Cross"],
            "tube_stations": ["Oxford Circus", "Piccadilly Circus"],
            "bus_stations": ["Victoria Coach Station", "Liverpool Street Bus Station"],
             "car_rental": "available",
            "taxis": "available"

        }
            },
            "tokyo": {
                "attractions": ["Tokyo Tower", "Meiji Shrine", "Sensoji Temple", "Tokyo Disneyland", "Ueno Park", "Shibuya Crossing", "Tokyo Skytree", "Asakusa", "Odaiba", "Roppongi Hills"],
                "weather": "Varied",
                "best_time_to_visit": "March to May and September to November",
                "boarding": "https://www.booking.com/city/jp/tokyo.en-gb.html",
                "travel_facilities": {
            "airports": ["Haneda Airport", "Narita International Airport"],
            "train_stations": ["Shinjuku Station", "Tokyo Station"],
            "subway_stations": ["Shibuya Station", "Asakusa Station"],
            "bus_stations": ["Tokyo Station Bus Terminal", "Shinjuku Expressway Bus Terminal"],
              "car_rental": "available",
            "taxis": "available"
                }

            },
            "sydney": {
                "attractions": ["Sydney Opera House", "Sydney Harbour Bridge", "Bondi Beach", "Taronga Zoo", "The Rocks", "Darling Harbour", "Royal Botanic Garden", "Manly Beach", "Queen Victoria Building", "Sea Life Sydney Aquarium"],
                "weather": "Warm summers and mild winters",
                "best_time_to_visit": "September to November and March to May",
                "boarding": "https://www.booking.com/city/au/sydney.en-gb.html",
                "travel_facilities": {
            "airports": ["Sydney Airport"],
            "train_stations": ["Central Station", "Circular Quay Station"],
            "metro_stations": ["Town Hall Station", "Wynyard Station"],
            "bus_stations": ["Sydney Central Bus Station", "Bondi Junction Bus Station"],
             "car_rental": "available",
            "taxis": "available"

        }


            },
            "rome": {
                "attractions": ["Colosseum", "Vatican Museums", "St. Peter's Basilica", "Pantheon", "Trevi Fountain", "Roman Forum", "Spanish Steps", "Piazza Navona", "Sistine Chapel", "Castel Sant'Angelo"],
                "weather": "Mediterranean climate",
                "best_time_to_visit": "October to April",
                "boarding": "https://www.booking.com/city/it/rome.en-gb.html",
                "travel_facilities": {
            "airports": ["Leonardo da Vinci International Airport"],
            "train_stations": ["Roma Termini", "Roma Tiburtina"],
            "metro_stations": ["Spagna", "Colosseo"],
            "bus_stations": ["Termini Bus Station", "Piazza Venezia"],
            "car_rental": "available",
            "taxis": "available"
                }

            },
            "bangkok": {
                "attractions": ["Grand Palace", "Wat Arun", "Wat Pho", "Chatuchak Market", "Jim Thompson House", "Lumphini Park", "Chao Phraya River", "Khao San Road", "MBK Center", "Siam Paragon"],
                "weather": "Hot and humid",
                "best_time_to_visit": "November to February",
                "boarding": "https://www.booking.com/city/th/bangkok.en-gb.html",
                "travel_facilities": {
            "airports": ["Suvarnabhumi Airport", "Don Mueang International Airport"],
            "train_stations": ["Hua Lamphong Railway Station", "Bangkok Railway Station"],
            "metro_stations": ["Sukhumvit", "Silom"],
            "bus_stations": ["Mo Chit Bus Terminal", "Southern Bus Terminal"],
             "car_rental": "available",
            "taxis": "available"
                }

            },
            "barcelona": {
                "attractions": ["Sagrada Familia", "Park Güell", "La Rambla", "Gothic Quarter", "Casa Batlló", "Camp Nou", "Montjuïc", "Picasso Museum", "Magic Fountain", "Barceloneta Beach"],
                "weather": "Mediterranean climate",
                "best_time_to_visit": "May to June and September to October",
                "boarding": "https://www.booking.com/city/es/barcelona.en-gb.html",
                 "travel_facilities": {
            "airports": ["Barcelona–El Prat Airport"],
            "train_stations": ["Barcelona Sants", "Passeig de Gràcia"],
            "metro_stations": ["Liceu", "Sagrada Familia"],
            "bus_stations": ["Estació del Nord"],
            "car_rental": "available",
            "taxis": "available"

                 }
            },
            "dubai": {
                "attractions": ["Burj Khalifa", "Dubai Mall", "Palm Jumeirah", "Dubai Marina", "Burj Al Arab", "Dubai Creek", "The Dubai Fountain", "Jumeirah Beach", "Dubai Aquarium", "Mall of the Emirates"],
                "weather": "Hot desert climate",
                "best_time_to_visit": "November to March",
                "boarding": "https://www.booking.com/city/ae/dubai.en-gb.html",
                 "travel_facilities": {
            "airports": ["Dubai International Airport"],
            "metro_stations": ["Burj Khalifa/Dubai Mall Station", "Dubai Marina Station"],
            "bus_stations": ["Al Ghubaiba Bus Station", "Ibn Battuta Bus Station"],
            "car_rental": "available",
            "taxis": "available"


        }
            },
            "singapore": {
                "attractions": ["Marina Bay Sands", "Gardens by the Bay", "Sentosa Island", "Universal Studios Singapore", "Orchard Road", "Singapore Zoo", "Clarke Quay", "Merlion Park", "Little India", "Chinatown"],
                "weather": "Tropical rainforest climate",
                "best_time_to_visit": "February to April",
                "boarding": "https://www.booking.com/city/sg/singapore.en-gb.html",
                "travel_facilities": {
            "airports": ["Singapore Changi Airport"],
            "train_stations": ["Changi Airport MRT Station", "City Hall MRT Station"],
            "metro_stations": ["Marina Bay MRT Station", "Chinatown MRT Station"],
            "bus_stations": ["Golden Mile Complex Bus Terminal", "Kallang Bahru Bus Terminal"],
               "car_rental": "available",
            "taxis": "available"
        }
           },
            "istanbul": {
                "attractions": ["Hagia Sophia", "Blue Mosque", "Topkapi Palace", "Grand Bazaar", "Basilica Cistern", "Galata Tower", "Dolmabahçe Palace", "Spice Bazaar", "Taksim Square", "Bosphorus Strait"],
                "weather": "Mediterranean climate",
                "best_time_to_visit": "April to May and September to November",
                "boarding": "https://www.booking.com/city/tr/istanbul.en-gb.html",
                "travel_facilities": {
            "airports": ["Istanbul Airport", "Sabiha Gökçen International Airport"],
            "train_stations": ["Sirkeci Station", "Haydarpaşa Station"],
            "metro_stations": ["Taksim", "Sultanahmet"],
            "bus_stations": ["Esenler Bus Terminal", "Harem Bus Terminal"],
              "car_rental": "available",
            "taxis": "available"
                }

            },
            "rio de janeiro": {
                "attractions": ["Christ the Redeemer", "Sugarloaf Mountain", "Copacabana Beach", "Ipanema Beach", "Tijuca National Park", "Maracanã Stadium", "Selarón Steps", "Santa Teresa", "Lapa Arches", "Botanical Garden"],
                "weather": "Tropical climate",
                "best_time_to_visit": "December to March",
                "boarding": "https://www.booking.com/city/br/rio-de-janeiro.en-gb.html",
                 "travel_facilities": {
            "airports": ["Rio de Janeiro–Galeão International Airport", "Santos Dumont Airport"],
            "train_stations": ["Central do Brasil Station"],
            "metro_stations": ["Siqueira Campos", "Cardeal Arcoverde"],
            "bus_stations": ["Rodoviária Novo Rio"],
             "car_rental": "available",
            "taxis": "available"
                }

            },
            "moscow": {
                "attractions": ["Red Square", "Kremlin", "Saint Basil's Cathedral", "Bolshoi Theatre", "Gorky Park", "Tretyakov Gallery", "VDNKh", "Moscow Metro", "Arbat Street", "Novodevichy Convent"],
                "weather": "Humid continental climate",
                "best_time_to_visit": "April to October",
                "boarding": "https://www.booking.com/city/ru/moscow.en-gb.html",
                "travel_facilities": {
            "airports": ["Sheremetyevo International Airport", "Domodedovo International Airport", "Vnukovo International Airport"],
            "train_stations": ["Moscow Leningradsky", "Moscow Yaroslavsky", "Moscow Kazansky"],
            "metro_stations": ["Komsomolskaya", "Kievskaya"],
            "bus_stations": ["Central Bus Station", "Varshavskaya Bus Station"],
              "car_rental": "available",
            "taxis": "available"
                }

            },
            "hong kong": {
                "attractions": ["Victoria Peak", "Tian Tan Buddha", "Hong Kong Disneyland", "Ladies' Market", "Ocean Park", "Temple Street Night Market", "Star Ferry", "Avenue of Stars", "Wong Tai Sin Temple", "Repulse Bay"],
                "weather": "Subtropical climate",
                "best_time_to_visit": "October to December",
                "boarding": "https://www.booking.com/city/hk/hong-kong.en-gb.html",
                "travel_facilities": {
            "airports": ["Hong Kong International Airport"],
            "train_stations": ["Hong Kong Station", "Kowloon Station"],
            "metro_stations": ["Central MTR Station", "Tsim Sha Tsui MTR Station"],
            "bus_stations": ["Hong Kong Central Bus Terminal", "Kowloon Bus Terminal"],
             "car_rental": "available",
            "taxis": "available"
                }

            },
            "cairo": {
                "attractions": ["Pyramids of Giza", "Egyptian Museum", "Khan el-Khalili", "Coptic Cairo", "Citadel of Saladin", "Al-Azhar Mosque", "Saqqara", "Cairo Tower", "The Sphinx", "Tahrir Square"],
                "weather": "Desert climate",
                "best_time_to_visit": "October to April",
                "boarding": "https://www.booking.com/city/eg/cairo.en-gb.html",
                "travel_facilities": {
            "airports": ["Cairo International Airport"],
            "train_stations": ["Ramses Station"],
            "metro_stations": ["Sadat", "Attaba"],
            "bus_stations": ["Torgoman Bus Station"],
             "car_rental": "available",
            "taxis": "available"
                }
            },
            "beijing": {
                "attractions": ["Great Wall of China", "Forbidden City", "Tiananmen Square", "Summer Palace", "Temple of Heaven", "Ming Tombs", "Beihai Park", "798 Art Zone", "Jingshan Park", "Lama Temple"],
                "weather": "Continental climate",
                "best_time_to_visit": "September to November",
                "boarding": "https://www.booking.com/city/cn/beijing.en-gb.html",
                 "travel_facilities": {
            "airports": ["Beijing Capital International Airport", "Beijing Daxing International Airport"],
            "train_stations": ["Beijing Railway Station", "Beijing West Railway Station", "Beijing South Railway Station"],
            "metro_stations": ["Tiananmen East", "Wangfujing"],
            "bus_stations": ["Liuliqiao Long-Distance Bus Station", "Zhaogongkou Long-Distance Bus Station"],
             "car_rental": "available",
            "taxis": "available"
                }
            },
            "kuala lumpur": {
                "attractions": ["Petronas Twin Towers", "Batu Caves", "Kuala Lumpur Bird Park", "Merdeka Square", "Bukit Bintang", "KLCC Park", "Thean Hou Temple", "Aquaria KLCC", "Jalan Alor", "National Mosque of Malaysia"],
                "weather": "Tropical rainforest climate",
                "best_time_to_visit": "May to July and December to February",
                "boarding": "https://www.booking.com/city/my/kuala-lumpur.en-gb.html",
                 "travel_facilities": {
            "airports": ["Kuala Lumpur International Airport"],
            "train_stations": ["KL Sentral"],
            "metro_stations": ["KLCC Station", "Bukit Bintang Station"],
            "bus_stations": ["Pasar Seni Bus Terminal", "Pudu Sentral"],
             "car_rental": "available",
            "taxis": "available"
                }

            },
            "kashmir": {
        "attractions": ["Dal Lake", "Gulmarg", "Srinagar", "Pahalgam", "Sonamarg", "Shalimar Bagh", "Shankaracharya Temple", "Hari Parbat", "Betaab Valley", "Tulip Garden"],
        "weather": "Varied",
        "best_time_to_visit": "March to October",
        "boarding": "https://www.goibibo.com/hotels/",
        "travel_facilities": {
            "airports": ["Sheikh ul-Alam International Airport (Srinagar Airport)"],
            "train_stations": ["Srinagar Railway Station"],
            "bus_stations": ["Lal Chowk Bus Stand", "Tourist Reception Center"],
            "car_rental": "available",
            "taxis": "available"
                }

    },
    "ladakh": {
        "attractions": ["Pangong Lake", "Nubra Valley", "Leh Palace", "Hemis Monastery", "Tso Moriri Lake", "Khardung La Pass", "Alchi Monastery", "Spituk Monastery", "Zanskar Valley", "Shanti Stupa"],
        "weather": "Varied",
        "best_time_to_visit": "June to September",
        "boarding": "https://www.goibibo.com/hotels/",
         "travel_facilities": {
            "airports": ["Kushok Bakula Rimpochee Airport (Leh Airport)"],
            "bus_stations": ["Leh Bus Stand"],
            "car_rental": "available",
            "taxis": "available"
                }

    },
    "rajasthan": {
        "attractions": ["Jaipur", "Udaipur", "Jaisalmer", "Jodhpur", "Ajmer", "Pushkar", "Mount Abu", "Ranthambore National Park", "Bikaner", "Chittorgarh"],
        "weather": "Varied",
        "best_time_to_visit": "October to March",
        "boarding": "https://www.goibibo.com/hotels/",
         "travel_facilities": {
            "airports": ["Jaipur International Airport", "Udaipur Airport", "Jodhpur Airport"],
            "train_stations": ["Jaipur Junction", "Udaipur City", "Jodhpur Junction"],
            "bus_stations": ["Jaipur Sindhi Camp Bus Stand", "Udaipur Roadways Bus Stand", "Jodhpur Roadways Bus Stand"],
             "car_rental": "available",
            "taxis": "available"
                }


    },
    "karnataka": {
        "attractions": ["Bangalore", "Mysore", "Hampi", "Coorg", "Gokarna", "Chikmagalur", "Udupi", "Bandipur National Park", "Halebidu", "Belur"],
        "weather": "Varied",
        "best_time_to_visit": "October to February",
        "boarding": "https://www.goibibo.com/hotels/",
         "travel_facilities": {
            "airports": ["Kempegowda International Airport (Bangalore Airport)"],
            "train_stations": ["Bangalore City Railway Station", "Mysore Junction"],
            "metro_stations": ["Bangalore Metro - Kempegowda Station", "Mysore Metro - Maharaja's College Station"],
            "bus_stations": ["Bangalore Majestic Bus Stand", "Mysore City Bus Stand"],
             "car_rental": "available",
            "taxis": "available"
                }
    },
    "uttar pradesh": {
        "attractions": ["Varanasi", "Agra", "Allahabad", "Lucknow", "Mathura", "Vrindavan", "Ayodhya", "Fatehpur Sikri", "Sarnath", "Kanpur"],
        "weather": "Varied",
        "best_time_to_visit": "October to March",
        "boarding": "https://www.goibibo.com/hotels/",
         "travel_facilities": {
            "airports": ["Chaudhary Charan Singh International Airport (Lucknow Airport)", "Lal Bahadur Shastri International Airport (Varanasi Airport)"],
            "train_stations": ["Lucknow Junction", "Varanasi Junction"],
            "bus_stations": ["Lucknow Alambagh Bus Stand", "Varanasi Cantt Bus Stand"],
            "car_rental": "available",
            "taxis": "available"
                }


    },
    "tamil nadu": {
        "attractions": ["Chennai", "Madurai", "Ooty", "Coimbatore", "Kodaikanal", "Mahabalipuram", "Rameswaram", "Thanjavur", "Kanyakumari", "Tiruchirappalli"],
        "weather": "Varied",
        "best_time_to_visit": "October to March",
        "boarding": "https://www.goibibo.com/hotels/",
        "travel_facilities": {
            "airports": ["Chennai International Airport", "Madurai Airport", "Coimbatore International Airport"],
            "train_stations": ["Chennai Central", "Madurai Junction", "Coimbatore Junction"],
            "bus_stations": ["Chennai Mofussil Bus Terminus", "Madurai Mattuthavani Bus Terminus", "Gandhipuram Central Bus Terminus (Coimbatore)"],
             "car_rental": "available",
            "taxis": "available"
                }


    },
            "jaipur": {
            "attractions": ["Amber Fort", "City Palace", "Hawa Mahal", "Jantar Mantar", "Jaigarh Fort", "Nahargarh Fort", "Albert Hall Museum", "Birla Mandir", "Jaipur Zoo", "Chokhi Dhani"],
            "weather": "Varied",
            "best_time_to_visit": "October to March",
            "boarding": "https://www.goibibo.com/hotels/",
            "travel_facilities": {
                "airports": ["Jaipur International Airport"],
                "train_stations": ["Jaipur Junction"],
                "bus_stations": ["Sindhi Camp Bus Stand"],
                "car_rental": "available",
                "taxis": "available"
            }
            },

  "agra": {
    "attractions": ["Taj Mahal", "Agra Fort", "Fatehpur Sikri", "Itmad-ud-Daulah's Tomb", "Mehtab Bagh"],
    "weather": "Varied",
    "best_time_to_visit": "October to March",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
      "airports": [],
      "train_stations": ["Agra Cantonment", "Agra Fort"],
      "bus_stations": ["Idgah Bus Stand", "Taj Depot"],
      "car_rental": "available",
      "taxis": "available"
    }
  },
  "kerala": {
    "attractions": ["Backwaters (Alleppey, Kumarakom)", "Munnar", "Periyar National Park", "Wayanad", "Fort Kochi"],
    "weather": "Tropical climate",
    "best_time_to_visit": "September to March",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
      "airports": ["Cochin International Airport", "Trivandrum International Airport", "Calicut International Airport"],
      "train_stations": ["Ernakulam Junction", "Trivandrum Central", "Kozhikode Railway Station"],
      "bus_stations": ["KSRTC Bus Stand (Thiruvananthapuram)", "KSRTC Bus Stand (Kochi)"],
      "car_rental": "available",
      "taxis": "available"
    }
  },
  "uttarakhand": {
    "attractions": ["Rishikesh", "Haridwar", "Nainital", "Mussoorie", "Jim Corbett National Park"],
    "weather": "Varied",
    "best_time_to_visit": "March to June, September to November",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
      "airports": ["Jolly Grant Airport (Dehradun)", "Pantnagar Airport"],
      "train_stations": ["Dehradun Railway Station", "Haridwar Junction"],
      "bus_stations": ["ISBT Dehradun", "Rishikesh Bus Stand"],
      "car_rental": "available",
      "taxis": "available"
    }
  },
  "punjab": {
    "attractions": ["Golden Temple (Amritsar)", "Wagah Border", "Jallianwala Bagh", "Anandpur Sahib", "Patiala"],
    "weather": "Varied",
    "best_time_to_visit": "October to March",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
      "airports": ["Sri Guru Ram Dass Jee International Airport (Amritsar)", "Chandigarh International Airport"],
      "train_stations": ["Amritsar Junction", "Ludhiana Junction"],
      "bus_stations": ["ISBT Amritsar", "ISBT Ludhiana"],
      "car_rental": "available",
      "taxis": "available"
    }
  },
  "kolkata": {
    "attractions": ["Victoria Memorial", "Howrah Bridge", "Dakshineswar Kali Temple", "Indian Museum", "Sundarbans"],
    "weather": "Varied",
    "best_time_to_visit": "October to March",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
      "airports": ["Netaji Subhas Chandra Bose International Airport"],
      "train_stations": ["Howrah Junction", "Sealdah Railway Station"],
      "metro_stations": ["Esplanade", "Park Street"],
      "bus_stations": ["Esplanade Bus Station", "Babughat Bus Stand"],
      "car_rental": "available",
      "taxis": "available"
    }
  },
  "darjeeling": {
    "attractions": ["Tiger Hill", "Batasia Loop", "Darjeeling Himalayan Railway", "Peace Pagoda", "Padmaja Naidu Himalayan Zoological Park"],
    "weather": "Cool climate",
    "best_time_to_visit": "October to March",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
      "airports": [],
      "train_stations": ["New Jalpaiguri Railway Station"],
      "bus_stations": ["Darjeeling Bus Stand"],
      "car_rental": "available",
      "taxis": "available"
    }
  },
  "shimla": {
    "attractions": ["The Ridge", "Jakhu Temple", "Mall Road", "Christ Church", "Kufri", "Shimla State Museum", "Annandale", "Indian Institute of Advanced Study", "Summer Hill", "Tara Devi Temple"],
    "weather": "Cool and pleasant",
    "best_time_to_visit": "March to June and September to November",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
        "airports": ["Shimla Airport (Jubbarhatti Airport)"],
        "train_stations": ["Kalka Railway Station"],
        "bus_stations": ["Tutikandi Bus Station", "Inter State Bus Terminal (ISBT)"],
        "car_rental": "available",
        "taxis": "available"
    }
},
"assam": {
    "attractions": ["Kaziranga National Park", "Kamakhya Temple", "Majuli Island", "Manas National Park", "Assam State Zoo", "Sualkuchi", "Hajo", "Umananda Island", "Pobitora Wildlife Sanctuary", "Dibrugarh"],
    "weather": "Varied",
    "best_time_to_visit": "October to April",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
        "airports": ["Lokpriya Gopinath Bordoloi International Airport (Guwahati Airport)"],
        "train_stations": ["Guwahati Railway Station", "Dibrugarh Railway Station"],
        "bus_stations": ["Guwahati ISBT", "Dibrugarh Bus Stand"],
        "car_rental": "available",
        "taxis": "available"
    }
},
"odisha": {
    "attractions": ["Puri Beach", "Konark Sun Temple", "Jagannath Temple", "Chilika Lake", "Udayagiri and Khandagiri Caves", "Bhitarkanika National Park", "Ratnagiri", "Lingaraja Temple", "Nandan Kanan Zoological Park", "Sambalpur"],
    "weather": "Varied",
    "best_time_to_visit": "November to February",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
        "airports": ["Biju Patnaik International Airport (Bhubaneswar Airport)"],
        "train_stations": ["Bhubaneswar Railway Station", "Puri Railway Station"],
        "bus_stations": ["Baramunda Bus Stand (Bhubaneswar)", "Puri Bus Stand"],
        "car_rental": "available",
        "taxis": "available"
    }
},
"andaman_and_nicobar": {
    "attractions": ["Radhanagar Beach", "Cellular Jail", "Havelock Island", "Neil Island", "Ross Island", "Baratang Island", "Port Blair", "Mahatma Gandhi Marine National Park", "Elephant Beach", "North Bay Island"],
    "weather": "Tropical climate",
    "best_time_to_visit": "November to April",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
        "airports": ["Veer Savarkar International Airport (Port Blair Airport)"],
        "ferry_terminals": ["Phoenix Bay Jetty (Port Blair)", "Havelock Jetty"],
        "car_rental": "limited availability",
        "taxis": "available"
    }
},
            "telangana": {
    "attractions": ["Charminar", "Golconda Fort", "Ramoji Film City", "Hussain Sagar Lake", "Birla Mandir", "Salar Jung Museum", "Chowmahalla Palace", "Golkonda", "Nehru Zoological Park", "Falaknuma Palace"],
    "weather": "Varied",
    "best_time_to_visit": "October to March",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
        "airports": ["Rajiv Gandhi International Airport (Hyderabad Airport)"],
        "train_stations": ["Hyderabad Deccan Railway Station"],
        "metro_stations": ["Ameerpet Metro Station", "L.B. Nagar Metro Station"],
        "bus_stations": ["Mahatma Gandhi Bus Station (MGBS)", "Jubilee Bus Station (JBS)"],
        "car_rental": "available",
        "taxis": "available"
    }
},
"andhra_pradesh": {
    "attractions": ["Tirupati Temple", "Araku Valley", "Borra Caves", "Belum Caves", "Sri Venkateswara National Park", "Kailasagiri", "Vizag Beaches", "Kondaveedu Fort", "Lepakshi", "Papikondalu"],
    "weather": "Varied",
    "best_time_to_visit": "November to February",
    "boarding": "https://www.goibibo.com/hotels/",
    "travel_facilities": {
        "airports": ["Visakhapatnam International Airport"],
        "train_stations": ["Visakhapatnam Railway Station", "Vijayawada Railway Station"],
        "bus_stations": ["Visakhapatnam RTC Complex", "Vijayawada Bus Stand"],
        "car_rental": "available",
        "taxis": "available"
    }
}

        }

        # Load spaCy NLP model
        self.nlp = spacy.load("en_core_web_sm")


    def get_destination_details(self, destination, query):
        destination_info = self.destinations.get(destination.lower())
        if destination_info:
            query = query.lower().strip()
            if query == "attractions":
                return ", ".join(destination_info["attractions"])
            elif query == "weather":
                return destination_info["weather"]
            elif query == "best_time_to_visit":
                return destination_info["best_time_to_visit"]
            elif query =="travel_facilities":
                return destination_info["travel_facilities"]
            elif query == "boarding":
                return destination_info.get("boarding", "Boarding information not available.")
            else:
                return "Invalid query. Please ask about attractions, weather, best time to visit, booking website, or boarding."
        else:
            return "Destination not found."

    def generate_trip_plan(self, destination, num_days):
        if destination.lower() not in self.destinations:
            return f"Destination {destination} not found."

        trip_plan = {}
        attractions = self.destinations[destination.lower()]["attractions"]
        attractions_per_day = len(attractions) // num_days
        start_index = 0

        for day in range(1, num_days + 1):
            end_index = min(start_index + attractions_per_day, len(attractions))
            trip_plan[f"Day {day}"] = attractions[start_index:end_index]
            start_index = end_index

        remaining_attractions = attractions[start_index:]
        if remaining_attractions:
            for day in range(1, len(remaining_attractions) + 1):
                trip_plan[f"Day {day}"].append(remaining_attractions[day - 1])

        return trip_plan

    def process_input(self, input_text):
        doc = self.nlp(input_text)
        destination = None
        query = None
        num_days = None

        # Extract destination and query from user input
        token_list = [token.text.lower() for token in doc]
        for i in range(len(token_list)):
            for j in range(i + 1, len(token_list) + 1):
                destination_text = ' '.join(token_list[i:j])
                if destination_text in self.destinations:
                    destination = destination_text
                    query = ' '.join(token_list[j:])
                    break
            if destination:
                break

        if destination:
            if "trip plan" in query:
                query_tokens = query.split()
                for token in query_tokens:
                    if token.isdigit():
                        num_days = int(token)
                        break
                if num_days:
                    trip_plan = self.generate_trip_plan(destination, num_days)
                    trip_plan_str = "\n".join([f"{day}: {', '.join(attractions)}" for day, attractions in trip_plan.items()])
                    return f"Trip plan for {destination}:\n{trip_plan_str}"
                else:
                    return "Please specify the number of days for the trip plan."
            else:
                if not query:
                    query = input_text.replace(destination, '').strip()
                return self.get_destination_details(destination, query)
        else:
            return "Invalid input. Please specify both destination and query."

# Example usage
chatbot = TripPlanner()

while True:
    user_input = input("You: ").strip()

    if user_input.lower() == "exit":
        print("Chatbot: Goodbye!")
        break
    else:
        response = chatbot.process_input(user_input)
        print("Chatbot:", response)
