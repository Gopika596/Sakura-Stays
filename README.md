# Sakura-Stays
import { MapPin, Star, Wifi, Utensils, Car, Bed, Home, Calendar, Leaf, Heart } from 'lucide-react'

const App = (props) => {
  const { location = "Kyoto, Japan" } = props

  const hotels = [
    {
      id: 1,
      image: "https://i.pinimg.com/originals/8b/de/7a/8bde7a9726147531b36600ef7f20a8c8.png",
      rating: 4.7,
      reviews: 6,
      title: "Sakura Haven Kyoto",
      description: "A boutique hotel offering vegetarian breakfast and a central location in Kyoto. It's praised for its excellent service and traditional Japanese hospitality.",
      amenities: ["Free Wi-Fi", "Kitchen", "4 Beds"],
      features: ["House", "Spa", "Central"],
      price: 180,
      period: "night"
    },
    {
      id: 2,
      image: "https://assets-global.website-files.com/63e4a910016aa3a65d8434e2/64917e8e4bc89d9efbaf4b85_Entrance01.jpg",
      rating: 4.6,
      reviews: 8,
      title: "Sakura Haven Kyoto",
      description: "Located in Nakagyo Ward, this hotel is known for its helpful staff, great location, and additional amenities that enhance the guest experience.",
      amenities: ["Free Wi-Fi", "Kitchen", "2 Beds"],
      features: ["Room", "Massage", "Central"],
      price: 66,
      period: "night"
    },
    {
      id: 3,
      image: "https://urbanpixxels.com/wp-content/uploads/14-11376-post/Koyoto-Ryokan-Hiiragiya-Traditional-Wing.jpg",
      rating: 4.7,
      reviews: 8,
      title: "Sakura Haven Kyoto",
      description: "Situated in Shimogyo Ward, it features spacious rooms and is ideal for families and groups. Highly recommended for its comfort and convenience.",
      amenities: ["Free Wi-Fi", "Restaurant"],
      features: ["2 Beds", "Room", "Massage"],
      price: 205,
      period: "night"
    },
    {
      id: 4,
      image: "https://payload108.cargocollective.com/1/6/215239/4478395/Hoshinoya-Kyoto-Japan-photo-by-Jonathan-Savoie-12_2048.jpg",
      rating: 4.7,
      reviews: 8,
      title: "Sakura Haven",
      description: "A contemporary hotel with modern amenities and public baths. Located near major attractions and transportation hubs.",
      amenities: ["Free Wi-Fi"],
      features: ["House"],
      price: 120,
      period: "night"
    }
  ]

  return (
    <div className="travel-homepage">
      {/* Header */}
      <header className="header">
        <div className="nav-container">
          <div className="logo">Voyago</div>
          <nav className="nav-menu">
            <a href="#" className="nav-link active">Homepage</a>
            <a href="#" className="nav-link">Vacation</a>
            <a href="#" className="nav-link">Hotels</a>
            <a href="#" className="nav-link">All in One</a>
            <a href="#" className="nav-link">Car Rental</a>
          </nav>
          <div className="header-actions">
            <div className="location-selector">
              <MapPin size={16} />
              <span>{location}</span>
            </div>
            <button className="register-btn">Register</button>
          </div>
        </div>
      </header>

      {/* Hero Section */}
      <main className="hero-section">
        <div className="hero-content">
          <h1 className="hero-title">
            Start Your Journey to Your<br />
            Dream Destination Here.
          </h1>
          <p className="hero-description">
            Start your journey to the destination you've always dreamed of. Discover stunning locations, plan
            with ease, and create memories that last a lifetime. Whether it's a relaxing escape or an exciting
            adventure, your perfect getaway begins right here.
          </p>
          
          <div className="action-buttons">
            <button className="action-btn">
              <Home size={16} />
              Hotels
            </button>
            <button className="action-btn">
              <Car size={16} />
              Car Rental
            </button>
            <button className="action-btn">
              <Calendar size={16} />
              Events
            </button>
          </div>
        </div>

        {/* Hotels Section */}
        <section className="hotels-section">
          <div className="section-header">
            <h2 className="section-title">Best hotels in</h2>
            <div className="location-badge">
              <MapPin size={16} />
              <span>{location}</span>
            </div>
          </div>

          <div className="hotels-grid">
            {hotels.map((hotel) => (
              <div key={hotel.id} className="hotel-card">
                <div className="hotel-image">
                  <img src={hotel.image} alt={hotel.title} />
                  <div className="rating-badge">
                    <Star size={12} fill="white" />
                    <span>{hotel.rating}/5</span>
                  </div>
                  <button className="favorite-btn">
                    <Heart size={16} />
                  </button>
                </div>
                
                <div className="hotel-info">
                  <h3 className="hotel-title">{hotel.title}</h3>
                  <p className="hotel-description">{hotel.description}</p>
                  
                  <div className="amenities">
                    {hotel.amenities.map((amenity, index) => (
                      <span key={index} className="amenity-tag">
                        {amenity === "Free Wi-Fi" && <Wifi size={12} />}
                        {amenity === "Kitchen" && <Utensils size={12} />}
                        {amenity === "Restaurant" && <Utensils size={12} />}
                        {amenity.includes("Beds") && <Bed size={12} />}
                        {amenity}
                      </span>
                    ))}
                  </div>
                  
                  <div className="features">
                    {hotel.features.map((feature, index) => (
                      <span key={index} className="feature-tag">
                        {feature === "House" && <Home size={12} />}
                        {feature === "Spa" && <Leaf size={12} />}
                        {feature === "Room" && <Bed size={12} />}
                        {feature}
                      </span>
                    ))}
                  </div>
                  
                  <div className="price">
                    <span className="price-amount">${hotel.price}</span>
                    <span className="price-period">/{hotel.period}</span>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </section>

        {/* Footer */}
        <footer className="footer">
          <div className="partner-logos">
            <span className="partner-logo">Booking.com</span>
            <span className="partner-logo">airbnb</span>
            <span className="partner-logo">Expedia</span>
            <span className="partner-logo">tripadvisor</span>
            <span className="partner-logo">Outdoorsy</span>
          </div>
        </footer>
      </main>

      <style>
        {`
          .travel-homepage {
            min-height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), 
                        url('https://backiee.com/static/wallpapers/1920x1080/207132.jpg');
            background-size: cover;
            background-position: center;
            color: white;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
          }

          .header {
            padding: 20px 0;
            position: relative;
            z-index: 10;
          }

          .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
          }

          .logo {
            font-size: 24px;
            font-weight: bold;
          }

          .nav-menu {
            display: flex;
            gap: 30px;
          }

          .nav-link {
            color: white;
            text-decoration: none;
            font-size: 14px;
            opacity: 0.8;
            transition: opacity 0.3s;
          }

          .nav-link.active,
          .nav-link:hover {
            opacity: 1;
          }

          .header-actions {
            display: flex;
            align-items: center;
            gap: 20px;
          }

          .location-selector {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 14px;
          }

          .register-btn {
            background: white;
            color: #333;
            border: none;
            padding: 8px 20px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
          }

          .hero-section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 60px 20px;
          }

          .hero-content {
            text-align: center;
            margin-bottom: 80px;
          }

          .hero-title {
            font-size: 48px;
            font-weight: bold;
            margin-bottom: 20px;
            line-height: 1.2;
          }

          .hero-description {
            font-size: 16px;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto 40px;
            line-height: 1.6;
          }

          .action-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
          }

          .action-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            color: white;
            padding: 12px 24px;
            border-radius: 25px;
            display: flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            font-size: 14px;
            transition: background 0.3s;
          }

          .action-btn:hover {
            background: rgba(255, 255, 255, 0.3);
          }

          .hotels-section {
            margin-bottom: 60px;
          }

          .section-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 30px;
          }

          .section-title {
            font-size: 24px;
            font-weight: 600;
            margin: 0;
          }

          .location-badge {
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(255, 255, 255, 0.2);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 14px;
          }

          .hotels-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
          }

          .hotel-card {
            background: rgba(0, 0, 0, 0.7);
            border-radius: 16px;
            overflow: hidden;
            backdrop-filter: blur(10px);
          }

          .hotel-image {
            position: relative;
            height: 200px;
            overflow: hidden;
          }

          .hotel-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
          }

          .rating-badge {
            position: absolute;
            top: 12px;
            left: 12px;
            background: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 4px 8px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            gap: 4px;
            font-size: 12px;
          }

          .favorite-btn {
            position: absolute;
            top: 12px;
            right: 12px;
            background: rgba(0, 0, 0, 0.7);
            border: none;
            color: white;
            width: 32px;
            height: 32px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
          }

          .hotel-info {
            padding: 20px;
          }

          .hotel-title {
            font-size: 18px;
            font-weight: 600;
            margin: 0 0 8px 0;
          }

          .hotel-description {
            font-size: 14px;
            opacity: 0.8;
            line-height: 1.4;
            margin: 0 0 16px 0;
          }

          .amenities {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 12px;
          }

          .amenity-tag {
            background: rgba(255, 255, 255, 0.1);
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 12px;
            display: flex;
            align-items: center;
            gap: 4px;
          }

          .features {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 16px;
          }

          .feature-tag {
            background: rgba(255, 255, 255, 0.1);
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 12px;
            display: flex;
            align-items: center;
            gap: 4px;
          }

          .price {
            display: flex;
            align-items: baseline;
            gap: 4px;
          }

          .price-amount {
            font-size: 24px;
            font-weight: bold;
          }

          .price-period {
            font-size: 14px;
            opacity: 0.7;
          }

          .footer {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
          }

          .partner-logos {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 40px;
            flex-wrap: wrap;
          }

          .partner-logo {
            font-size: 16px;
            opacity: 0.7;
            font-weight: 500;
          }

          @media (max-width: 768px) {
            .nav-menu {
              display: none;
            }
            
            .hero-title {
              font-size: 32px;
            }
            
            .action-buttons {
              flex-direction: column;
              align-items: center;
            }
            
            .hotels-grid {
              grid-template-columns: 1fr;
            }
            
            .partner-logos {
              gap: 20px;
            }
          }
        `}
      </style>
    </div>
  )
}

export default App
