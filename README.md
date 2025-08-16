```jsx
import { useState, useEffect, useRef } from "react";
import {
  Home,
  Video,
  Image,
  Music,
  MessageCircle,
  Users,
  Shield,
  Gamepad2,
  Sparkles,
  Search,
  Plus,
  Send,
  Heart,
  Share2,
  MoreVertical,
  User,
  LogOut,
  Moon,
  Sun,
  Play,
  Pause,
  Mic,
  VideoIcon,
  Camera,
  File,
  ThumbsUp,
  MessageSquare,
  Phone,
  Video as VideoCall,
  Bell,
  Settings,
  HelpCircle,
  BookOpen,
  Crown,
  Star,
  Zap,
  Lock,
  Fingerprint,
  ShieldCheck,
  Globe,
  PhoneCall,
  RefreshCw,
  Upload,
  Smile,
  Gift,
  TrendingUp,
  ChartBar,
  Code,
  Brain,
  Bot,
  LayoutGrid,
  List,
  Grid,
  AlignLeft,
  Calendar,
  Clock,
  MapPin,
  Tag,
  X,
  Check,
  Download,
  ExternalLink,
  Volume2,
  VolumeX,
  Maximize2,
  Minimize2
} from "lucide-react";

const App = () => {
  const [activeTab, setActiveTab] = useState("home");
  const [darkMode, setDarkMode] = useState(true);
  const [user, setUser] = useState({
    name: "Usuario Qnnop",
    avatar: "https://placehold.co/40/6366f1/ffffff?text=Q",
    status: "En línea",
    premium: true
  });
  const [posts, setPosts] = useState([
    {
      id: 1,
      user: "María García",
      avatar: "https://placehold.co/40/ec4899/ffffff?text=MG",
      content: "Explorando nuevas ideas para el proyecto escolar 🎓✨",
      image: "https://placehold.co/400x600/f3f4f6/6b7280?text=Proyecto+Escolar",
      likes: 156,
      comments: 23,
      shares: 8,
      timestamp: "2h ago",
      type: "post",
      music: "Classical Study - Focus Flow"
    },
    {
      id: 2,
      user: "Carlos Rodríguez",
      avatar: "https://placehold.co/40/10b981/ffffff?text=CR",
      content: "Nuevo equipo de estudio creado para matemáticas avanzadas! Únete si estás interesado 👇",
      image: "https://placehold.co/400x600/10b981/ffffff?text=Equipo+Matemáticas",
      likes: 89,
      comments: 15,
      shares: 12,
      timestamp: "4h ago",
      type: "team",
      members: 12,
      subject: "Matemáticas Avanzadas"
    },
    {
      id: 3,
      user: "Ana López",
      avatar: "https://placehold.co/40/f59e0b/ffffff?text=AL",
      content: "¡Mi primer Qnnop Rell! Practicando con la IA para mejorar mis habilidades de presentación 🎤",
      video: "https://placehold.co/240x426/8b5cf6/ffffff?text=Rell+IA",
      likes: 234,
      comments: 45,
      shares: 28,
      timestamp: "6h ago",
      type: "reel",
      music: "Electronic Beat - Energy Boost",
      views: "12.5K"
    },
    {
      id: 4,
      user: "Qwen IA",
      avatar: "https://placehold.co/40/06b6d4/ffffff?text=AI",
      content: "Hola equipo! Estoy aquí para ayudar con cualquier duda académica o de proyecto. Pregunta lo que necesites saber 🤖✨",
      image: "https://placehold.co/400x600/06b6d4/ffffff?text=IA+Asistente",
      likes: 500,
      comments: 89,
      shares: 45,
      timestamp: "8h ago",
      type: "ai",
      verified: true
    }
  ]);
  const [stories, setStories] = useState([
    { id: 1, user: "Tú", avatar: "https://placehold.co/60/6366f1/ffffff?text=Q", highlight: true, new: true },
    { id: 2, user: "María", avatar: "https://placehold.co/60/ec4899/ffffff?text=MG", highlight: true },
    { id: 3, user: "Carlos", avatar: "https://placehold.co/60/10b981/ffffff?text=CR", highlight: true },
    { id: 4, user: "Ana", avatar: "https://placehold.co/60/f59e0b/ffffff?text=AL", highlight: true },
    { id: 5, user: "Qwen IA", avatar: "https://placehold.co/60/06b6d4/ffffff?text=AI", highlight: true, verified: true },
    { id: 6, user: "Equipo Proyecto", avatar: "https://placehold.co/60/8b5cf6/ffffff?text=E", team: true }
  ]);
  const [chats, setChats] = useState([
    {
      id: 1,
      name: "Grupo Matemáticas Avanzadas",
      avatar: "https://placehold.co/40/10b981/ffffff?text=M",
      lastMessage: "¿Alguien tiene el ejercicio 15 resuelto?",
      timestamp: "10 min ago",
      unread: 3,
      type: "group",
      members: 12,
      online: 8
    },
    {
      id: 2,
      name: "María García",
      avatar: "https://placehold.co/40/ec4899/ffffff?text=MG",
      lastMessage: "¡Gracias por la ayuda con el proyecto!",
      timestamp: "30 min ago",
      unread: 1,
      type: "direct",
      online: true
    },
    {
      id: 3,
      name: "Qwen IA",
      avatar: "https://placehold.co/40/06b6d4/ffffff?text=AI",
      lastMessage: "¿En qué puedo ayudarte hoy?",
      timestamp: "1h ago",
      unread: 0,
      type: "ai",
      online: true,
      verified: true
    },
    {
      id: 4,
      name: "Equipo Final Proyecto",
      avatar: "https://placehold.co/40/8b5cf6/ffffff?text=P",
      lastMessage: "Reunión programada para mañana a las 4pm",
      timestamp: "2h ago",
      unread: 2,
      type: "team",
      members: 5,
      online: 3
    }
  ]);
  const [teams, setTeams] = useState([
    {
      id: 1,
      name: "Matemáticas Avanzadas",
      description: "Grupo de estudio para cálculo integral y diferencial",
      members: 12,
      online: 8,
      subject: "Matemáticas",
      level: "Universidad",
      createdAt: "2 semanas ago",
      avatar: "https://placehold.co/60/10b981/ffffff?text=M"
    },
    {
      id: 2,
      name: "Proyecto Final Ingeniería",
      description: "Desarrollo de aplicación móvil para educación",
      members: 5,
      online: 3,
      subject: "Ingeniería de Software",
      level: "Universidad",
      createdAt: "1 mes ago",
      avatar: "https://placehold.co/60/8b5cf6/ffffff?text=P"
    },
    {
      id: 3,
      name: "Ciencias Naturales",
      description: "Preparación para examen de biología y química",
      members: 8,
      online: 5,
      subject: "Biología",
      level: "Secundaria",
      createdAt: "3 semanas ago",
      avatar: "https://placehold.co/60/f59e0b/ffffff?text=C"
    }
  ]);
  const [games, setGames] = useState([
    {
      id: 1,
      name: "Qnnop Quiz",
      image: "https://placehold.co/200x120/8b5cf6/ffffff?text=Quiz",
      players: "1.2K en línea",
      category: "Educación"
    },
    {
      id: 2,
      name: "Brain Challenge",
      image: "https://placehold.co/200x120/06b6d4/ffffff?text=Cerebro",
      players: "856 en línea",
      category: "Inteligencia"
    },
    {
      id: 3,
      name: "Math Arena",
      image: "https://placehold.co/200x120/10b981/ffffff?text=Math",
      players: "678 en línea",
      category: "Matemáticas"
    },
    {
      id: 4,
      name: "Code Battle",
      image: "https://placehold.co/200x120/ec4899/ffffff?text=Code",
      players: "432 en línea",
      category: "Programación"
    }
  ]);
  const [showCreatePost, setShowCreatePost] = useState(false);
  const [createType, setCreateType] = useState("post");
  const [securityLevel, setSecurityLevel] = useState("high");
  const [notifications, setNotifications] = useState([
    { id: 1, type: "like", user: "María García", content: "le dio me gusta a tu publicación", time: "5 min ago", read: false },
    { id: 2, type: "comment", user: "Carlos Rodríguez", content: "comentó en tu rell: ¡Excelente trabajo!", time: "15 min ago", read: false },
    { id: 3, type: "team", user: "Equipo Matemáticas", content: "te invitó a unirte al equipo", time: "30 min ago", read: true },
    { id: 4, type: "ai", user: "Qwen IA", content: "ha analizado tu proyecto y tiene sugerencias", time: "1h ago", read: true }
  ]);
  const [currentMusic, setCurrentMusic] = useState(null);
  const [isPlaying, setIsPlaying] = useState(false);
  const [showSecurityPanel, setShowSecurityPanel] = useState(false);
  const [showQuickGuide, setShowQuickGuide] = useState(false);
  const [activeChat, setActiveChat] = useState(null);
  const [showVideoCall, setShowVideoCall] = useState(false);
  const fileInputRef = useRef(null);

  const handleCreatePost = (e) => {
    e.preventDefault();
    const formData = new FormData(e.target);
    const newPost = {
      id: posts.length + 1,
      user: user.name,
      avatar: user.avatar,
      content: formData.get('content'),
      likes: 0,
      comments: 0,
      shares: 0,
      timestamp: "ahora",
      type: createType
    };
    
    if (createType === "reel") {
      newPost.video = "https://placehold.co/240x426/8b5cf6/ffffff?text=Nuevo+Rell";
      newPost.views = "0";
      newPost.music = formData.get('music') || "Sin música";
    } else if (createType === "post") {
      const file = formData.get('image');
      if (file && file.size > 0) {
        newPost.image = URL.createObjectURL(file);
      }
      newPost.music = formData.get('music') || null;
    }
    
    setPosts([newPost, ...posts]);
    setShowCreatePost(false);
    e.target.reset();
  };

  const handleLike = (postId) => {
    setPosts(posts.map(post => 
      post.id === postId 
        ? { ...post, likes: post.likes + 1 }
        : post
    ));
  };

  const handleShare = (postId) => {
    setPosts(posts.map(post => 
      post.id === postId 
        ? { ...post, shares: post.shares + 1 }
        : post
    ));
  };

  const startVideoCall = (chat) => {
    setActiveChat(chat);
    setShowVideoCall(true);
  };

  const SecurityFeature = ({ icon: Icon, title, description, level }) => (
    <div className="bg-white dark:bg-gray-800 rounded-xl p-6 shadow-lg border border-gray-200 dark:border-gray-700 hover:shadow-xl transition-all duration-300">
      <div className="flex items-center mb-4">
        <div className="p-3 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full text-white mr-4">
          <Icon size={24} />
        </div>
        <div>
          <h4 className="font-bold text-gray-800 dark:text-white">{title}</h4>
          <span className={`text-xs px-2 py-1 rounded-full ${
            level === 'high' ? 'bg-green-100 text-green-800 dark:bg-green-900 dark:text-green-200' :
            level === 'medium' ? 'bg-yellow-100 text-yellow-800 dark:bg-yellow-900 dark:text-yellow-200' :
            'bg-red-100 text-red-800 dark:bg-red-900 dark:text-red-200'
          }`}>
            {level === 'high' ? 'Alto' : level === 'medium' ? 'Medio' : 'Bajo'}
          </span>
        </div>
      </div>
      <p className="text-gray-600 dark:text-gray-300 text-sm leading-relaxed">{description}</p>
    </div>
  );

  const QuickGuideStep = ({ number, title, description, icon: Icon }) => (
    <div className="flex items-start space-x-4 p-4 bg-white dark:bg-gray-800 rounded-xl shadow-md hover:shadow-lg transition-all duration-300">
      <div className="flex-shrink-0 w-8 h-8 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center text-white font-bold text-sm">
        {number}
      </div>
      <div className="flex-1">
        <div className="flex items-center mb-2">
          <Icon size={20} className="text-purple-500 mr-2" />
          <h4 className="font-semibold text-gray-800 dark:text-white">{title}</h4>
        </div>
        <p className="text-gray-600 dark:text-gray-300 text-sm">{description}</p>
      </div>
    </div>
  );

  return (
    <div className={`min-h-screen transition-colors duration-300 ${darkMode ? 'dark bg-gray-900' : 'bg-gray-50'}`}>
      {/* Main Layout */}
      <div className="flex h-screen">
        {/* Sidebar */}
        <div className="w-20 lg:w-64 bg-white dark:bg-gray-800 shadow-lg flex flex-col transition-all duration-300 border-r border-gray-200 dark:border-gray-700">
          {/* Logo */}
          <div className="p-4 border-b border-gray-200 dark:border-gray-700">
            <div className="flex items-center space-x-3 lg:space-x-4">
              <div className="w-10 h-10 bg-gradient-to-r from-purple-500 via-pink-500 to-blue-500 rounded-xl flex items-center justify-center">
                <span className="text-white font-bold text-lg">Q</span>
              </div>
              <div className="hidden lg:block">
                <h1 className="text-xl font-bold bg-gradient-to-r from-purple-500 to-pink-500 bg-clip-text text-transparent">
                  Qnnop
                </h1>
                <p className="text-xs text-gray-500 dark:text-gray-400">Conectando el futuro</p>
              </div>
            </div>
          </div>

          {/* Navigation */}
          <nav className="flex-1 p-4">
            <ul className="space-y-2">
              {[
                { id: 'home', icon: Home, label: 'Inicio', notification: 3 },
                { id: 'reels', icon: Video, label: 'Rells', notification: 8 },
                { id: 'stories', icon: Camera, label: 'Estados', notification: 5 },
                { id: 'chats', icon: MessageCircle, label: 'Chats', notification: 4 },
                { id: 'teams', icon: Users, label: 'Equipos', notification: 2 },
                { id: 'games', icon: Gamepad2, label: 'Juegos', notification: 12 },
                { id: 'ai', icon: Brain, label: 'Qwen IA', notification: 6 }
              ].map((item) => (
                <li key={item.id}>
                  <button
                    onClick={() => setActiveTab(item.id)}
                    className={`w-full flex items-center space-x-3 lg:space-x-4 px-3 py-3 rounded-xl transition-all duration-200 ${
                      activeTab === item.id
                        ? 'bg-gradient-to-r from-purple-500 to-pink-500 text-white shadow-lg'
                        : 'text-gray-600 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700'
                    }`}
                  >
                    <item.icon size={20} />
                    <span className="hidden lg:block font-medium">{item.label}</span>
                    {item.notification > 0 && (
                      <span className="ml-auto bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
                        {item.notification}
                      </span>
                    )}
                  </button>
                </li>
              ))}
            </ul>
          </nav>

          {/* User Profile */}
          <div className="p-4 border-t border-gray-200 dark:border-gray-700">
            <div className="flex items-center space-x-3">
              <img
                src={user.avatar}
                alt={user.name}
                className="w-10 h-10 rounded-full border-2 border-purple-500"
              />
              <div className="hidden lg:block flex-1 min-w-0">
                <p className="text-sm font-semibold text-gray-800 dark:text-white truncate">
                  {user.name}
                </p>
                <div className="flex items-center space-x-1">
                  <div className="w-2 h-2 bg-green-500 rounded-full"></div>
                  <span className="text-xs text-gray-500 dark:text-gray-400">{user.status}</span>
                </div>
              </div>
              <button
                onClick={() => setDarkMode(!darkMode)}
                className="p-2 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-600 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-600 transition-colors"
              >
                {darkMode ? <Sun size={16} /> : <Moon size={16} />}
              </button>
            </div>
          </div>
        </div>

        {/* Main Content */}
        <div className="flex-1 flex flex-col">
          {/* Header */}
          <header className="bg-white dark:bg-gray-800 shadow-sm border-b border-gray-200 dark:border-gray-700 px-6 py-4">
            <div className="flex items-center justify-between">
              <div className="flex-1 max-w-lg">
                <div className="relative">
                  <Search className="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-400" size={20} />
                  <input
                    type="text"
                    placeholder="Buscar en Qnnop..."
                    className="w-full pl-10 pr-4 py-2 bg-gray-100 dark:bg-gray-700 border-0 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 text-gray-800 dark:text-white"
                  />
                </div>
              </div>
              
              <div className="flex items-center space-x-4 ml-6">
                <button
                  onClick={() => setShowSecurityPanel(true)}
                  className="p-2 rounded-lg bg-red-500 text-white hover:bg-red-600 transition-colors"
                >
                  <Shield size={20} />
                </button>
                
                <button
                  onClick={() => setShowQuickGuide(true)}
                  className="p-2 rounded-lg bg-blue-500 text-white hover:bg-blue-600 transition-colors"
                >
                  <BookOpen size={20} />
                </button>
                
                <button
                  onClick={() => setNotifications(notifications.map(n => ({...n, read: true})))}
                  className="relative p-2 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-600 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-600 transition-colors"
                >
                  <Bell size={20} />
                  {notifications.filter(n => !n.read).length > 0 && (
                    <span className="absolute -top-1 -right-1 bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
                      {notifications.filter(n => !n.read).length}
                    </span>
                  )}
                </button>
                
                <button
                  onClick={() => setShowCreatePost(true)}
                  className="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-4 py-2 rounded-xl hover:shadow-lg transition-all duration-200 flex items-center space-x-2"
                >
                  <Plus size={16} />
                  <span className="hidden sm:block">Crear</span>
                </button>
              </div>
            </div>
          </header>

          {/* Content Area */}
          <main className="flex-1 overflow-y-auto p-6">
            {activeTab === 'home' && (
              <div className="max-w-4xl mx-auto">
                {/* Stories */}
                <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-6 mb-6 border border-gray-200 dark:border-gray-700">
                  <div className="flex items-center justify-between mb-4">
                    <h2 className="text-xl font-bold text-gray-800 dark:text-white">Estados</h2>
                    <button className="text-purple-500 hover:text-purple-600 text-sm font-medium">
                      Ver todo
                    </button>
                  </div>
                  <div className="flex space-x-4 overflow-x-auto pb-2">
                    {stories.map((story) => (
                      <div key={story.id} className="flex flex-col items-center space-y-2 flex-shrink-0">
                        <div className={`relative p-0.5 rounded-full ${
                          story.new ? 'bg-gradient-to-r from-purple-500 to-pink-500' : 'bg-gray-300 dark:bg-gray-600'
                        }`}>
                          <img
                            src={story.avatar}
                            alt={story.user}
                            className="w-16 h-16 rounded-full border-4 border-white dark:border-gray-800"
                          />
                          {story.verified && (
                            <div className="absolute -bottom-1 -right-1 bg-blue-500 rounded-full p-1">
                              <Check size={12} className="text-white" />
                            </div>
                          )}
                        </div>
                        <span className="text-xs text-gray-600 dark:text-gray-300 text-center w-16 truncate">
                          {story.user}
                        </span>
                      </div>
                    ))}
                  </div>
                </div>

                {/* Posts */}
                <div className="space-y-6">
                  {posts.map((post) => (
                    <div key={post.id} className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg overflow-hidden border border-gray-200 dark:border-gray-700">
                      {/* Post Header */}
                      <div className="p-6 pb-4">
                        <div className="flex items-center space-x-3">
                          <img
                            src={post.avatar}
                            alt={post.user}
                            className="w-10 h-10 rounded-full"
                          />
                          <div className="flex-1">
                            <div className="flex items-center space-x-2">
                              <h3 className="font-semibold text-gray-800 dark:text-white">{post.user}</h3>
                              {post.verified && (
                                <div className="bg-blue-500 rounded-full p-1">
                                  <Check size={12} className="text-white" />
                                </div>
                              )}
                              {post.premium && (
                                <div className="bg-gradient-to-r from-yellow-400 to-orange-500 rounded-full p-1">
                                  <Crown size={12} className="text-white" />
                                </div>
                              )}
                            </div>
                            <p className="text-sm text-gray-500 dark:text-gray-400">{post.timestamp}</p>
                          </div>
                          <button className="p-2 hover:bg-gray-100 dark:hover:bg-gray-700 rounded-lg">
                            <MoreVertical size={20} className="text-gray-500 dark:text-gray-400" />
                          </button>
                        </div>
                      </div>

                      {/* Post Content */}
                      <div className="px-6 pb-4">
                        <p className="text-gray-800 dark:text-white mb-4">{post.content}</p>
                        
                        {post.image && (
                          <div className="rounded-xl overflow-hidden mb-4">
                            <img
                              src={post.image}
                              alt="Post content"
                              className="w-full h-auto object-cover"
                            />
                          </div>
                        )}
                        
                        {post.video && (
                          <div className="rounded-xl overflow-hidden mb-4 relative">
                            <img
                              src={post.video}
                              alt="Rell content"
                              className="w-full h-auto object-cover"
                            />
                            <div className="absolute inset-0 flex items-center justify-center">
                              <div className="bg-black bg-opacity-50 rounded-full p-4">
                                <Play size={32} className="text-white" />
                              </div>
                            </div>
                            {post.views && (
                              <div className="absolute top-4 right-4 bg-black bg-opacity-70 text-white px-2 py-1 rounded-full text-sm">
                                {post.views}
                              </div>
                            )}
                          </div>
                        )}
                        
                        {post.music && (
                          <div className="flex items-center space-x-2 bg-gray-100 dark:bg-gray-700 rounded-lg p-3 mb-4">
                            <Music size={16} className="text-purple-500" />
                            <span className="text-sm text-gray-700 dark:text-gray-300">{post.music}</span>
                            <button
                              onClick={() => {
                                setCurrentMusic(post.music);
                                setIsPlaying(!isPlaying);
                              }}
                              className="ml-auto text-purple-500 hover:text-purple-600"
                            >
                              {isPlaying && currentMusic === post.music ? <Pause size={16} /> : <Play size={16} />}
                            </button>
                          </div>
                        )}
                      </div>

                      {/* Post Actions */}
                      <div className="px-6 py-4 border-t border-gray-200 dark:border-gray-700">
                        <div className="flex items-center justify-between">
                          <div className="flex items-center space-x-6">
                            <button
                              onClick={() => handleLike(post.id)}
                              className="flex items-center space-x-2 text-gray-600 dark:text-gray-300 hover:text-red-500 dark:hover:text-red-400 transition-colors"
                            >
                              <Heart size={20} />
                              <span className="font-medium">{post.likes}</span>
                            </button>
                            
                            <button className="flex items-center space-x-2 text-gray-600 dark:text-gray-300 hover:text-blue-500 dark:hover:text-blue-400 transition-colors">
                              <MessageSquare size={20} />
                              <span className="font-medium">{post.comments}</span>
                            </button>
                            
                            <button
                              onClick={() => handleShare(post.id)}
                              className="flex items-center space-x-2 text-gray-600 dark:text-gray-300 hover:text-green-500 dark:hover:text-green-400 transition-colors"
                            >
                              <Share2 size={20} />
                              <span className="font-medium">{post.shares}</span>
                            </button>
                          </div>
                          
                          <button className="flex items-center space-x-2 text-gray-600 dark:text-gray-300 hover:text-purple-500 dark:hover:text-purple-400 transition-colors">
                            <Send size={20} />
                            <span className="hidden sm:block">Enviar</span>
                          </button>
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            )}

            {activeTab === 'reels' && (
              <div className="max-w-6xl mx-auto">
                <div className="flex items-center justify-between mb-6">
                  <h1 className="text-3xl font-bold bg-gradient-to-r from-purple-500 to-pink-500 bg-clip-text text-transparent">
                    Qnnop Rells
                  </h1>
                  <div className="flex items-center space-x-2">
                    <button className="px-4 py-2 bg-gray-100 dark:bg-gray-700 rounded-lg text-gray-700 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-600 transition-colors">
                      Recomendados
                    </button>
                    <button className="px-4 py-2 bg-purple-500 text-white rounded-lg hover:bg-purple-600 transition-colors">
                      Para ti
                    </button>
                  </div>
                </div>
                
                <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                  {posts.filter(p => p.type === 'reel').map((reel) => (
                    <div key={reel.id} className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg overflow-hidden border border-gray-200 dark:border-gray-700">
                      <div className="relative pb-[150%]">
                        <img
                          src={reel.video}
                          alt="Rell"
                          className="absolute inset-0 w-full h-full object-cover"
                        />
                        <div className="absolute inset-0 bg-black bg-opacity-20 flex items-center justify-center">
                          <div className="bg-black bg-opacity-50 rounded-full p-4">
                            <Play size={32} className="text-white" />
                          </div>
                        </div>
                        <div className="absolute bottom-4 left-4 right-4">
                          <div className="bg-black bg-opacity-70 text-white p-3 rounded-lg">
                            <p className="font-medium">{reel.content}</p>
                            <div className="flex items-center space-x-2 mt-2">
                              <Music size={14} />
                              <span className="text-sm">{reel.music}</span>
                            </div>
                          </div>
                        </div>
                      </div>
                      
                      <div className="p-4">
                        <div className="flex items-center space-x-3 mb-3">
                          <img
                            src={reel.avatar}
                            alt={reel.user}
                            className="w-8 h-8 rounded-full"
                          />
                          <span className="font-medium text-gray-800 dark:text-white">{reel.user}</span>
                        </div>
                        
                        <div className="flex items-center justify-between">
                          <div className="flex items-center space-x-4">
                            <button className="flex items-center space-x-1 text-gray-600 dark:text-gray-300 hover:text-red-500 dark:hover:text-red-400 transition-colors">
                              <Heart size={18} />
                              <span className="text-sm">{reel.likes}</span>
                            </button>
                            <button className="flex items-center space-x-1 text-gray-600 dark:text-gray-300 hover:text-blue-500 dark:hover:text-blue-400 transition-colors">
                              <MessageSquare size={18} />
                              <span className="text-sm">{reel.comments}</span>
                            </button>
                          </div>
                          <span className="text-sm text-gray-500 dark:text-gray-400">{reel.views}</span>
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            )}

            {activeTab === 'chats' && (
              <div className="max-w-4xl mx-auto">
                <div className="flex items-center justify-between mb-6">
                  <h1 className="text-3xl font-bold bg-gradient-to-r from-purple-500 to-pink-500 bg-clip-text text-transparent">
                    Chats
                  </h1>
                  <button
                    onClick={() => setShowCreatePost(true)}
                    className="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-6 py-2 rounded-xl hover:shadow-lg transition-all duration-200 flex items-center space-x-2"
                  >
                    <Plus size={18} />
                    <span>Nuevo Chat</span>
                  </button>
                </div>
                
                <div className="grid grid-cols-1 lg:grid-cols-3 gap-6">
                  {/* Chat List */}
                  <div className="lg:col-span-1">
                    <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-6 border border-gray-200 dark:border-gray-700">
                      <div className="mb-4">
                        <div className="relative">
                          <Search className="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-400" size={16} />
                          <input
                            type="text"
                            placeholder="Buscar chat..."
                            className="w-full pl-10 pr-4 py-2 bg-gray-100 dark:bg-gray-700 border-0 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 text-gray-800 dark:text-white text-sm"
                          />
                        </div>
                      </div>
                      
                      <div className="space-y-3">
                        {chats.map((chat) => (
                          <div
                            key={chat.id}
                            onClick={() => setActiveChat(chat)}
                            className={`flex items-center space-x-3 p-3 rounded-xl cursor-pointer transition-all duration-200 ${
                              activeChat?.id === chat.id
                                ? 'bg-gradient-to-r from-purple-500 to-pink-500 text-white'
                                : 'hover:bg-gray-100 dark:hover:bg-gray-700 text-gray-800 dark:text-white'
                            }`}
                          >
                            <div className="relative">
                              <img
                                src={chat.avatar}
                                alt={chat.name}
                                className="w-12 h-12 rounded-full"
                              />
                              {chat.online && (
                                <div className="absolute -bottom-1 -right-1 w-4 h-4 bg-green-500 border-2 border-white dark:border-gray-800 rounded-full"></div>
                              )}
                            </div>
                            
                            <div className="flex-1 min-w-0">
                              <div className="flex items-center space-x-2">
                                <h4 className="font-medium truncate">{chat.name}</h4>
                                {chat.verified && (
                                  <Check size={14} className="text-blue-300" />
                                )}
                              </div>
                              <p className="text-sm text-gray-500 dark:text-gray-400 truncate">
                                {chat.lastMessage}
                              </p>
                            </div>
                            
                            <div className="text-right">
                              <p className="text-xs text-gray-500 dark:text-gray-400">{chat.timestamp}</p>
                              {chat.unread > 0 && (
                                <div className="bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center mt-1 ml-auto">
                                  {chat.unread}
                                </div>
                              )}
                            </div>
                          </div>
                        ))}
                      </div>
                    </div>
                  </div>
                  
                  {/* Chat Content */}
                  <div className="lg:col-span-2">
                    {activeChat ? (
                      <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg border border-gray-200 dark:border-gray-700 flex flex-col h-96">
                        {/* Chat Header */}
                        <div className="p-4 border-b border-gray-200 dark:border-gray-700 flex items-center justify-between">
                          <div className="flex items-center space-x-3">
                            <img
                              src={activeChat.avatar}
                              alt={activeChat.name}
                              className="w-10 h-10 rounded-full"
                            />
                            <div>
                              <h3 className="font-semibold text-gray-800 dark:text-white">{activeChat.name}</h3>
                              <div className="flex items-center space-x-2">
                                <div className={`w-2 h-2 rounded-full ${activeChat.online ? 'bg-green-500' : 'bg-gray-400'}`}></div>
                                <span className="text-xs text-gray-500 dark:text-gray-400">
                                  {activeChat.online ? 'En línea' : 'Desconectado'}
                                </span>
                              </div>
                            </div>
                          </div>
                          
                          <div className="flex items-center space-x-2">
                            <button
                              onClick={() => startVideoCall(activeChat)}
                              className="p-2 bg-green-500 text-white rounded-lg hover:bg-green-600 transition-colors"
                            >
                              <VideoCall size={18} />
                            </button>
                            <button
                              onClick={() => startVideoCall(activeChat)}
                              className="p-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition-colors"
                            >
                              <PhoneCall size={18} />
                            </button>
                            <button className="p-2 text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200">
                              <MoreVertical size={18} />
                            </button>
                          </div>
                        </div>
                        
                        {/* Messages */}
                        <div className="flex-1 p-4 overflow-y-auto">
                          <div className="space-y-4">
                            <div className="flex justify-end">
                              <div className="bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-2xl rounded-tr-none px-4 py-2 max-w-xs">
                                <p className="text-sm">Hola! ¿Cómo estás? Estoy trabajando en el proyecto de matemáticas.</p>
                              </div>
                            </div>
                            
                            <div className="flex justify-start">
                              <div className="bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white rounded-2xl rounded-tl-none px-4 py-2 max-w-xs">
                                <p className="text-sm">Hola! Yo bien, gracias. ¿Necesitas ayuda con algo específico?</p>
                              </div>
                            </div>
                            
                            <div className="flex justify-end">
                              <div className="bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-2xl rounded-tr-none px-4 py-2 max-w-xs">
                                <p className="text-sm">Sí, tengo dudas con el ejercicio 15 del capítulo 3. ¿Podrías explicármelo?</p>
                              </div>
                            </div>
                            
                            <div className="flex justify-start">
                              <div className="bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white rounded-2xl rounded-tl-none px-4 py-2 max-w-xs">
                                <p className="text-sm">Claro! Envíame una foto del ejercicio y te ayudo enseguida.</p>
                              </div>
                            </div>
                          </div>
                        </div>
                        
                        {/* Message Input */}
                        <div className="p-4 border-t border-gray-200 dark:border-gray-700">
                          <div className="flex items-center space-x-2">
                            <button className="p-2 text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200">
                              <Smile size={20} />
                            </button>
                            <button
                              onClick={() => fileInputRef.current?.click()}
                              className="p-2 text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
                            >
                              <Paperclip size={20} />
                            </button>
                            <input
                              ref={fileInputRef}
                              type="file"
                              className="hidden"
                              accept="image/*,video/*"
                            />
                            <input
                              type="text"
                              placeholder="Escribe un mensaje..."
                              className="flex-1 bg-gray-100 dark:bg-gray-700 border-0 rounded-full px-4 py-2 focus:outline-none focus:ring-2 focus:ring-purple-500 text-gray-800 dark:text-white"
                            />
                            <button className="p-2 bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-full hover:shadow-lg transition-all duration-200">
                              <Send size={20} />
                            </button>
                          </div>
                        </div>
                      </div>
                    ) : (
                      <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-12 border border-gray-200 dark:border-gray-700 flex flex-col items-center justify-center text-center">
                        <MessageCircle size={64} className="text-gray-300 dark:text-gray-600 mb-4" />
                        <h3 className="text-xl font-semibold text-gray-800 dark:text-white mb-2">Selecciona un chat</h3>
                        <p className="text-gray-500 dark:text-gray-400">Elige un chat de la lista para comenzar una conversación.</p>
                      </div>
                    )}
                  </div>
                </div>
              </div>
            )}

            {activeTab === 'teams' && (
              <div className="max-w-6xl mx-auto">
                <div className="flex items-center justify-between mb-6">
                  <h1 className="text-3xl font-bold bg-gradient-to-r from-purple-500 to-pink-500 bg-clip-text text-transparent">
                    Equipos de Estudio
                  </h1>
                  <button
                    onClick={() => setShowCreatePost(true)}
                    className="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-6 py-2 rounded-xl hover:shadow-lg transition-all duration-200 flex items-center space-x-2"
                  >
                    <Plus size={18} />
                    <span>Crear Equipo</span>
                  </button>
                </div>
                
                <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                  {teams.map((team) => (
                    <div key={team.id} className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg overflow-hidden border border-gray-200 dark:border-gray-700 hover:shadow-xl transition-all duration-300">
                      <div className="p-6">
                        <div className="flex items-center space-x-4 mb-4">
                          <img
                            src={team.avatar}
                            alt={team.name}
                            className="w-16 h-16 rounded-xl"
                          />
                          <div className="flex-1">
                            <h3 className="text-xl font-bold text-gray-800 dark:text-white">{team.name}</h3>
                            <p className="text-sm text-gray-500 dark:text-gray-400">{team.subject} • {team.level}</p>
                          </div>
                        </div>
                        
                        <p className="text-gray-600 dark:text-gray-300 mb-4 text-sm leading-relaxed">
                          {team.description}
                        </p>
                        
                        <div className="flex items-center justify-between mb-4">
                          <div className="flex items-center space-x-4 text-sm">
                            <div className="flex items-center space-x-1">
                              <Users size={14} className="text-gray-500 dark:text-gray-400" />
                              <span className="text-gray-600 dark:text-gray-300">{team.members}</span>
                            </div>
                            <div className="flex items-center space-x-1">
                              <div className="w-2 h-2 bg-green-500 rounded-full"></div>
                              <span className="text-gray-600 dark:text-gray-300">{team.online} en línea</span>
                            </div>
                          </div>
                        </div>
                        
                        <div className="flex space-x-2">
                          <button className="flex-1 bg-gradient-to-r from-purple-500 to-pink-500 text-white py-2 rounded-lg hover:shadow-lg transition-all duration-200 font-medium">
                            Unirse
                          </button>
                          <button className="px-4 py-2 border border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700 transition-colors">
                            <Share2 size={16} />
                          </button>
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            )}

            {activeTab === 'games' && (
              <div className="max-w-6xl mx-auto">
                <div className="flex items-center justify-between mb-6">
                  <h1 className="text-3xl font-bold bg-gradient-to-r from-purple-500 to-pink-500 bg-clip-text text-transparent">
                    Centro de Juegos
                  </h1>
                  <div className="flex items-center space-x-2">
                    <button className="px-4 py-2 bg-gray-100 dark:bg-gray-700 rounded-lg text-gray-700 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-600 transition-colors">
                      Todos
                    </button>
                    <button className="px-4 py-2 bg-purple-500 text-white rounded-lg hover:bg-purple-600 transition-colors">
                      Populares
                    </button>
                  </div>
                </div>
                
                <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                  {games.map((game) => (
                    <div key={game.id} className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg overflow-hidden border border-gray-200 dark:border-gray-700 hover:shadow-xl transition-all duration-300">
                      <img
                        src={game.image}
                        alt={game.name}
                        className="w-full h-32 object-cover"
                      />
                      <div className="p-4">
                        <h3 className="font-bold text-gray-800 dark:text-white mb-2">{game.name}</h3>
                        <p className="text-sm text-gray-500 dark:text-gray-400 mb-3">{game.players}</p>
                        <div className="flex items-center justify-between">
                          <span className="text-xs bg-purple-100 dark:bg-purple-900 text-purple-800 dark:text-purple-200 px-2 py-1 rounded-full">
                            {game.category}
                          </span>
                          <button className="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-3 py-1 rounded-lg text-sm hover:shadow-lg transition-all duration-200">
                            Jugar
                          </button>
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
                
                <div className="mt-12 bg-gradient-to-r from-purple-500 to-pink-500 rounded-2xl p-8 text-white text-center">
                  <h2 className="text-2xl font-bold mb-4">¿Quieres crear tu propio juego?</h2>
                  <p className="mb-6 opacity-90">Únete a nuestra comunidad de desarrolladores y crea juegos educativos que ayuden a otros estudiantes.</p>
                  <button className="bg-white text-purple-500 px-8 py-3 rounded-xl font-semibold hover:shadow-lg transition-all duration-200">
                    Comenzar a Desarrollar
                  </button>
                </div>
              </div>
            )}

            {activeTab === 'ai' && (
              <div className="max-w-4xl mx-auto">
                <div className="bg-gradient-to-r from-blue-500 to-cyan-500 rounded-2xl p-8 mb-6 text-white">
                  <div className="flex items-center space-x-4 mb-4">
                    <div className="w-16 h-16 bg-white bg-opacity-20 rounded-full flex items-center justify-center">
                      <Bot size={32} />
                    </div>
                    <div>
                      <h1 className="text-3xl font-bold">Qwen IA</h1>
                      <p className="opacity-90">Tu asistente de inteligencia artificial para el aprendizaje</p>
                    </div>
                  </div>
                </div>
                
                <div className="grid grid-cols-1 lg:grid-cols-2 gap-6">
                  <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-6 border border-gray-200 dark:border-gray-700">
                    <h3 className="text-xl font-bold text-gray-800 dark:text-white mb-4">Funciones de IA</h3>
                    <div className="space-y-4">
                      {[
                        { icon: Code, title: "Ayuda con Programación", desc: "Resuelve dudas de código y mejora tus habilidades" },
                        { icon: BookOpen, title: "Resúmenes Académicos", desc: "Obtén resúmenes de libros y artículos científicos" },
                        { icon: Brain, title: "Práctica de Exámenes", desc: "Simulacros personalizados para tus materias" },
                        { icon: Sparkles, title: "Ideas Creativas", desc: "Genera ideas para proyectos y presentaciones" }
                      ].map((feature, index) => (
                        <div key={index} className="flex items-start space-x-3 p-3 bg-gray-50 dark:bg-gray-700 rounded-lg">
                          <div className="p-2 bg-blue-100 dark:bg-blue-900 text-blue-600 dark:text-blue-300 rounded-lg">
                            <feature.icon size={18} />
                          </div>
                          <div>
                            <h4 className="font-semibold text-gray-800 dark:text-white">{feature.title}</h4>
                            <p className="text-sm text-gray-600 dark:text-gray-300">{feature.desc}</p>
                          </div>
                        </div>
                      ))}
                    </div>
                  </div>
                  
                  <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-6 border border-gray-200 dark:border-gray-700">
                    <h3 className="text-xl font-bold text-gray-800 dark:text-white mb-4">Chat con Qwen IA</h3>
                    <div className="h-64 bg-gray-50 dark:bg-gray-700 rounded-lg p-4 mb-4 overflow-y-auto">
                      <div className="space-y-4">
                        <div className="flex justify-start">
                          <div className="bg-blue-100 dark:bg-blue-900 text-blue-800 dark:text-blue-200 rounded-2xl rounded-tl-none px-4 py-2 max-w-xs">
                            <p className="text-sm">Hola! ¿En qué puedo ayudarte hoy?</p>
                          </div>
                        </div>
                        <div className="flex justify-end">
                          <div className="bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-white rounded-2xl rounded-tr-none px-4 py-2 max-w-xs">
                            <p className="text-sm">Necesito ayuda con un problema de cálculo integral.</p>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div className="flex space-x-2">
                      <input
                        type="text"
                        placeholder="Pregunta algo a Qwen IA..."
                        className="flex-1 bg-gray-100 dark:bg-gray-700 border-0 rounded-full px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500 text-gray-800 dark:text-white"
                      />
                      <button className="bg-gradient-to-r from-blue-500 to-cyan-500 text-white p-2 rounded-full hover:shadow-lg transition-all duration-200">
                        <Send size={20} />
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            )}
          </main>
        </div>
      </div>

      {/* Create Post Modal */}
      {showCreatePost && (
        <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
          <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-2xl max-w-md w-full max-h-96 overflow-y-auto">
            <div className="p-6 border-b border-gray-200 dark:border-gray-700">
              <div className="flex items-center justify-between">
                <h2 className="text-xl font-bold text-gray-800 dark:text-white">Crear Publicación</h2>
                <button
                  onClick={() => setShowCreatePost(false)}
                  className="p-2 text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
                >
                  <X size={20} />
                </button>
              </div>
            </div>
            
            <form onSubmit={handleCreatePost} className="p-6">
              <div className="flex space-x-2 mb-4">
                {['post', 'reel', 'story'].map((type) => (
                  <button
                    key={type}
                    type="button"
                    onClick={() => setCreateType(type)}
                    className={`flex-1 py-2 px-4 rounded-lg font-medium transition-colors ${
                      createType === type
                        ? 'bg-purple-500 text-white'
                        : 'bg-gray-100 dark:bg-gray-700 text-gray-700 dark:text-gray-300'
                    }`}
                  >
                    {type === 'post' ? 'Publicación' : type === 'reel' ? 'Rell' : 'Estado'}
                  </button>
                ))}
              </div>
              
              {createType === 'reel' ? (
                <div className="space-y-4">
                  <div className="border-2 border-dashed border-gray-300 dark:border-gray-600 rounded-xl p-8 text-center">
                    <VideoIcon size={48} className="mx-auto text-gray-400 mb-4" />
                    <p className="text-gray-600 dark:text-gray-300 mb-4">Selecciona un video para tu Rell</p>
                    <button
                      type="button"
                      className="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-6 py-2 rounded-lg hover:shadow-lg transition-all duration-200"
                    >
                      Seleccionar Video
                    </button>
                  </div>
                  
                  <div>
                    <label className="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">
                      Música para tu Rell
                    </label>
                    <input
                      type="text"
                      name="music"
                      placeholder="Buscar música..."
                      className="w-full px-3 py-2 bg-gray-100 dark:bg-gray-700 border-0 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 text-gray-800 dark:text-white"
                    />
                  </div>
                </div>
              ) : (
                <div className="space-y-4">
                  <textarea
                    name="content"
                    placeholder="¿Qué estás pensando?"
                    rows="3"
                    className="w-full px-3 py-2 bg-gray-100 dark:bg-gray-700 border-0 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 text-gray-800 dark:text-white resize-none"
                    required
                  ></textarea>
                  
                  {createType === 'post' && (
                    <div>
                      <label className="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">
                        Imagen (opcional)
                      </label>
                      <input
                        type="file"
                        name="image"
                        accept="image/*"
                        className="w-full px-3 py-2 bg-gray-100 dark:bg-gray-700 border-0 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 text-gray-800 dark:text-white"
                      />
                    </div>
                  )}
                  
                  <div>
                    <label className="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">
                      Música (opcional)
                    </label>
                    <input
                      type="text"
                      name="music"
                      placeholder="Agregar música..."
                      className="w-full px-3 py-2 bg-gray-100 dark:bg-gray-700 border-0 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 text-gray-800 dark:text-white"
                    />
                  </div>
                </div>
              )}
              
              <div className="flex space-x-3 mt-6">
                <button
                  type="button"
                  onClick={() => setShowCreatePost(false)}
                  className="flex-1 py-2 px-4 border border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700 transition-colors"
                >
                  Cancelar
                </button>
                <button
                  type="submit"
                  className="flex-1 py-2 px-4 bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-lg hover:shadow-lg transition-all duration-200"
                >
                  Publicar
                </button>
              </div>
            </form>
          </div>
        </div>
      )}

      {/* Security Panel */}
      {showSecurityPanel && (
        <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
          <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-2xl max-w-4xl w-full max-h-96 overflow-y-auto">
            <div className="p-6 border-b border-gray-200 dark:border-gray-700">
              <div className="flex items-center justify-between">
                <div className="flex items-center space-x-3">
                  <div className="p-2 bg-red-500 rounded-full">
                    <ShieldCheck size={24} className="text-white" />
                  </div>
                  <div>
                    <h2 className="text-xl font-bold text-gray-800 dark:text-white">Seguridad Qnnop</h2>
                    <p className="text-sm text-gray-500 dark:text-gray-400">Nivel de seguridad: {securityLevel}</p>
                  </div>
                </div>
                <button
                  onClick={() => setShowSecurityPanel(false)}
                  className="p-2 text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
                >
                  <X size={20} />
                </button>
              </div>
            </div>
            
            <div className="p-6">
              <div className="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                <SecurityFeature
                  icon={Fingerprint}
                  title="Autenticación Biométrica"
                  description="Acceso mediante huella digital o reconocimiento facial para mayor seguridad."
                  level="high"
                />
                <SecurityFeature
                  icon={Lock}
                  title="Cifrado de Extremo a Extremo"
                  description="Todos tus mensajes y archivos están completamente cifrados y solo tú puedes acceder a ellos."
                  level="high"
                />
                <SecurityFeature
                  icon={Globe}
                  title="Protección Global"
                  description="Sistema anti-hackeo con monitoreo 24/7 que detecta y bloquea amenazas en tiempo real."
                  level="high"
                />
                <SecurityFeature
                  icon={RefreshCw}
                  title="Sesiones Activas"
                  description="Control total sobre tus sesiones activas y posibilidad de cerrar sesiones remotas."
                  level="high"
                />
              </div>
              
              <div className="flex space-x-3">
                <button
                  onClick={() => setSecurityLevel("high")}
                  className={`flex-1 py-2 px-4 rounded-lg font-medium transition-colors ${
                    securityLevel === "high"
                      ? "bg-green-500 text-white"
                      : "bg-gray-100 dark:bg-gray-700 text-gray-700 dark:text-gray-300"
                  }`}
                >
                  Seguridad Alta
                </button>
                <button
                  onClick={() => setSecurityLevel("medium")}
                  className={`flex-1 py-2 px-4 rounded-lg font-medium transition-colors ${
                    securityLevel === "medium"
                      ? "bg-yellow-500 text-white"
                      : "bg-gray-100 dark:bg-gray-700 text-gray-700 dark:text-gray-300"
                  }`}
                >
                  Seguridad Media
                </button>
                <button
                  onClick={() => setSecurityLevel("low")}
                  className={`flex-1 py-2 px-4 rounded-lg font-medium transition-colors ${
                    securityLevel === "low"
                      ? "bg-red-500 text-white"
                      : "bg-gray-100 dark:bg-gray-700 text-gray-700 dark:text-gray-300"
                  }`}
                >
                  Seguridad Básica
                </button>
              </div>
            </div>
          </div>
        </div>
      )}

      {/* Quick Guide */}
      {showQuickGuide && (
        <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
          <div className="bg-white dark:bg-gray-800 rounded-2xl shadow-2xl max-w-2xl w-full max-h-96 overflow-y-auto">
            <div className="p-6 border-b border-gray-200 dark:border-gray-700">
              <div className="flex items-center justify-between">
                <div className="flex items-center space-x-3">
                  <div className="p-2 bg-blue-500 rounded-full">
                    <BookOpen size={24} className="text-white" />
                  </div>
                  <div>
                    <h2 className="text-xl font-bold text-gray-800 dark:text-white">Guía Rápida Qnnop</h2>
                    <p className="text-sm text-gray-500 dark:text-gray-400">Aprende a usar todas las funciones</p>
                  </div>
                </div>
                <button
                  onClick={() => setShowQuickGuide(false)}
                  className="p-2 text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
                >
                  <X size={20} />
                </button>
              </div>
            </div>
            
            <div className="p-6">
              <div className="space-y-4">
                <QuickGuideStep
                  number={1}
                  icon={Home}
                  title="Explora el Inicio"
                  description="Descubre publicaciones de tus amigos y equipos de estudio en tu feed principal."
                />
                <QuickGuideStep
                  number={2}
                  icon={Video}
                  title="Crea Rells"
                  description="Comparte tus conocimientos con videos cortos y música para mayor engagement."
                />
                <QuickGuideStep
                  number={3}
                  icon={MessageCircle}
                  title="Chatea con Equipos"
                  description="Colabora en tiempo real con tus compañeros de estudio en chats grupales."
                />
                <QuickGuideStep
                  number={4}
                  icon={Users}
                  title="Únete a Equipos"
                  description="Encuentra o crea equipos de estudio para materias específicas y niveles académicos."
                />
                <QuickGuideStep
                  number={5}
                  icon={Brain}
                  title="Consulta a Qwen IA"
                  description="Resuelve tus dudas académicas con nuestra inteligencia artificial avanzada."
                />
              </div>
            </div>
          </div>
        </div>
      )}

      {/* Video Call Modal */}
      {showVideoCall && activeChat && (
        <div className="fixed inset-0 bg-black bg-opacity-90 flex items-center justify-center z-50">
          <div className="relative w-full h-full">
            {/* Background Video */}
            <div className="absolute inset-0 bg-gradient-to-br from-purple-900 via-blue-900 to-indigo-900">
              <div className="absolute inset-0 bg-black bg-opacity-30"></div>
            </div>
            
            {/* Remote Video */}
            <div className="absolute inset-0 flex items-center justify-center">
              <div className="w-3/4 h-3/4 bg-black rounded-lg overflow-hidden border-4 border-white border-opacity-20">
                <img
                  src="https://placehold.co/800x600/1f2937/ffffff?text=Video+Remoto"
                  alt="Remote video"
                  className="w-full h-full object-cover"
                />
              </div>
            </div>
            
            {/* Local Video (Picture in Picture) */}
            <div className="absolute bottom-4 right-4 w-48 h-36 bg-black rounded-lg overflow-hidden border-2 border-white border-opacity-30">
              <img
                src={user.avatar.replace('text=Q', 'text=' + user.name.charAt(0))}
                alt="Your video"
                className="w-full h-full object-cover"
              />
            </div>
            
            {/* Call Controls */}
            <div className="absolute bottom-8 left-1/2 transform -translate-x-1/2 flex items-center space-x-6">
              <button className="p-4 bg-gray-800 bg-opacity-50 rounded-full hover:bg-opacity-70 transition-all">
                <Mic size={24} className="text-white" />
              </button>
              <button className="p-4 bg-red-500 rounded-full hover:bg-red-600 transition-all">
                <Phone size={24} className="text-white" />
              </button>
              <button className="p-4 bg-gray-800 bg-opacity-50 rounded-full hover:bg-opacity-70 transition-all">
                <VideoIcon size={24} className="text-white" />
              </button>
            </div>
            
            {/* Call Info */}
            <div className="absolute top-4 left-4 text-white">
              <h3 className="text-xl font-bold">{activeChat.name}</h3>
              <p className="text-sm opacity-90">Llamada de video en curso</p>
            </div>
            
            {/* Close Button */}
            <button
              onClick={() => setShowVideoCall(false)}
              className="absolute top-4 right-4 p-2 bg-black bg-opacity-50 rounded-full hover:bg-opacity-70 transition-all"
            >
              <X size={24} className="text-white" />
            </button>
          </div>
        </div>
      )}
    </div>
  );
};

export default App;
```
