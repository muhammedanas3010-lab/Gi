import React, { useState } from 'react';
import { 
  TrendingUp, 
  TrendingDown, 
  DollarSign, 
  ShoppingBag, 
  Clock, 
  Users, 
  PlusCircle, 
  UserPlus, 
  Calendar, 
  BarChart2, 
  Home, 
  PieChart 
} from 'lucide-react';

export default function App() {
  const [activeTab, setActiveTab] = useState('home');

  // Sample State Data
  const [metrics, setMetrics] = useState({
    totalRevenue: 250000,
    totalProfit: 95000,
    totalExpense: 155000,
    bebi: { profit: 55000, expense: 80000 },
    ledi: { profit: 40000, expense: 75000 },
    completedOrders: 142,
    remainingOrders: 18,
    totalEmployees: 6,
    nextDelivery: { name: "Aisha Rahman", date: "2026-10-03" }
  });

  return (
    <div className="flex justify-center items-center min-h-screen bg-gray-900 font-sans p-2">
      {/* Mobile Device Frame */}
      <div className="w-full max-w-md bg-[#0a1f18] text-white rounded-[40px] overflow-hidden shadow-2xl border-4 border-gray-800 flex flex-col min-h-[840px]">
        
        {/* Top Header */}
        <div className="p-6 pb-2 flex justify-between items-center pt-8">
          <div className="flex items-center space-x-3">
            <div className="w-10 h-10 rounded-full bg-emerald-700 flex items-center justify-center font-bold border-2 border-emerald-400">
              K
            </div>
            <div>
              <p className="text-xs text-gray-400">ഹലോ,</p>
              <h2 className="text-lg font-bold leading-none">Kaiz Sooq</h2>
            </div>
          </div>
          <button className="w-9 h-9 rounded-full bg-[#133328] flex items-center justify-center text-emerald-400">
            🔔
          </button>
        </div>

        {/* Scrollable Main Content */}
        <div className="flex-1 overflow-y-auto px-5 pt-3 pb-24 space-y-4">

          {/* Main Card: Total Revenue */}
          <div className="bg-gradient-to-br from-[#0f3d2e] to-[#0a291f] p-5 rounded-3xl border border-emerald-800/40 shadow-lg">
            <p className="text-xs text-emerald-300 font-medium">ആകെ വരുമാനം (Total Revenue)</p>
            <h1 className="text-3xl font-extrabold mt-1 text-white">
              ₹{metrics.totalRevenue.toLocaleString()}
            </h1>
            
            <div className="grid grid-cols-2 gap-3 mt-4 pt-3 border-t border-emerald-800/50">
              <div>
                <span className="text-[10px] text-gray-400 uppercase">Total Profit</span>
                <p className="text-sm font-semibold text-emerald-400 flex items-center gap-1">
                  <TrendingUp size={14} /> ₹{metrics.totalProfit.toLocaleString()}
                </p>
              </div>
              <div>
                <span className="text-[10px] text-gray-400 uppercase">Total Expense</span>
                <p className="text-sm font-semibold text-rose-400 flex items-center gap-1">
                  <TrendingDown size={14} /> ₹{metrics.totalExpense.toLocaleString()}
                </p>
              </div>
            </div>
          </div>

          {/* Brand-wise Profit & Expense (BEBI & LEDI) */}
          <div className="grid grid-cols-2 gap-3">
            {/* BEBI Card */}
            <div className="bg-[#133328] p-4 rounded-2xl border border-emerald-800/30">
              <div className="flex justify-between items-center mb-2">
                <span className="text-xs font-bold text-emerald-300 bg-emerald-950 px-2 py-0.5 rounded">BEBI</span>
              </div>
              <div className="text-xs text-gray-300">
                <p>Profit: <span className="font-semibold text-emerald-400">₹{metrics.bebi.profit}</span></p>
                <p className="mt-1">Exp: <span className="font-semibold text-rose-400">₹{metrics.bebi.expense}</span></p>
              </div>
            </div>

            {/* LEDI Card */}
            <div className="bg-[#133328] p-4 rounded-2xl border border-emerald-800/30">
              <div className="flex justify-between items-center mb-2">
                <span className="text-xs font-bold text-emerald-300 bg-emerald-950 px-2 py-0.5 rounded">LEDI</span>
              </div>
              <div className="text-xs text-gray-300">
                <p>Profit: <span className="font-semibold text-emerald-400">₹{metrics.ledi.profit}</span></p>
                <p className="mt-1">Exp: <span className="font-semibold text-rose-400">₹{metrics.ledi.expense}</span></p>
              </div>
            </div>
          </div>

          {/* Quick Action Buttons */}
          <div className="grid grid-cols-2 gap-3">
            <button className="flex items-center justify-center gap-2 bg-emerald-500 hover:bg-emerald-600 text-gray-950 font-semibold p-3 rounded-2xl transition">
              <PlusCircle size={18} />
              <span className="text-xs">Add New Order</span>
            </button>
            <button className="flex items-center justify-center gap-2 bg-[#1b4435] text-emerald-300 font-semibold p-3 rounded-2xl border border-emerald-700/50 hover:bg-[#225442] transition">
              <UserPlus size={18} />
              <span className="text-xs">Add Employee</span>
            </button>
          </div>

          {/* Next Delivery Highlight Card */}
          <div className="bg-emerald-950/60 p-4 rounded-2xl border border-emerald-500/30 flex items-center gap-3">
            <div className="p-3 bg-emerald-500/20 rounded-xl text-emerald-400">
              <Calendar size={20} />
            </div>
            <div className="flex-1">
              <p className="text-[10px] text-emerald-400 font-medium uppercase tracking-wider">അടുത്ത ഡെലിവറി (Next Delivery)</p>
              <h4 className="text-sm font-bold text-white">{metrics.nextDelivery.name}</h4>
              <p className="text-xs text-gray-400">തീയതി: {metrics.nextDelivery.date}</p>
            </div>
          </div>

          {/* Orders & Employees Overview */}
          <div className="bg-[#133328] p-4 rounded-2xl space-y-3">
            <h3 className="text-xs font-semibold text-gray-300 border-b border-emerald-800/40 pb-2">ആപ്പ് സ്ഥിതിവിവരക്കണക്കുകൾ</h3>
            
            <div className="grid grid-cols-3 gap-2 text-center">
              <div className="bg-[#0a291f] p-2 rounded-xl">
                <ShoppingBag size={16} className="mx-auto text-emerald-400 mb-1" />
                <p className="text-[10px] text-gray-400">Completed</p>
                <p className="text-sm font-bold text-white">{metrics.completedOrders}</p>
              </div>

              <div className="bg-[#0a291f] p-2 rounded-xl">
                <Clock size={16} className="mx-auto text-amber-400 mb-1" />
                <p className="text-[10px] text-gray-400">Remaining</p>
                <p className="text-sm font-bold text-white">{metrics.remainingOrders}</p>
              </div>

              <div className="bg-[#0a291f] p-2 rounded-xl">
                <Users size={16} className="mx-auto text-cyan-400 mb-1" />
                <p className="text-[10px] text-gray-400">Employees</p>
                <p className="text-sm font-bold text-white">{metrics.totalEmployees}</p>
              </div>
            </div>
          </div>

          {/* Date-based Analysis Option */}
          <div className="bg-[#133328] p-4 rounded-2xl flex justify-between items-center">
            <div className="flex items-center gap-3">
              <BarChart2 className="text-emerald-400" size={20} />
              <div>
                <h4 className="text-xs font-bold">Date-based Analysis</h4>
                <p className="text-[10px] text-gray-400">തീയതി അടിസ്ഥാനമാക്കിയുള്ള വിശകലനം</p>
              </div>
            </div>
            <button className="text-xs bg-emerald-500/20 text-emerald-300 px-3 py-1.5 rounded-lg border border-emerald-500/30">
              View Analytics
            </button>
          </div>

        </div>

        {/* Bottom Navigation Bar */}
        <div className="absolute bottom-0 w-full max-w-md bg-[#081a14] border-t border-emerald-900/40 py-3 px-6 flex justify-between items-center rounded-b-[40px]">
          <button 
            onClick={() => setActiveTab('home')}
            className={`flex flex-col items-center text-xs ${activeTab === 'home' ? 'text-emerald-400' : 'text-gray-500'}`}
          >
            <Home size={18} />
            <span className="text-[10px] mt-1">Home</span>
          </button>

          <button 
            onClick={() => setActiveTab('analytics')}
            className={`flex flex-col items-center text-xs ${activeTab === 'analytics' ? 'text-emerald-400' : 'text-gray-500'}`}
          >
            <BarChart2 size={18} />
            <span className="text-[10px] mt-1">Analytics</span>
          </button>

          {/* Floating Plus Icon */}
          <div className="-mt-8 bg-emerald-500 p-3 rounded-full text-gray-950 shadow-lg border-4 border-[#0a1f18]">
            <PlusCircle size={24} />
          </div>

          <button 
            onClick={() => setActiveTab('orders')}
            className={`flex flex-col items-center text-xs ${activeTab === 'orders' ? 'text-emerald-400' : 'text-gray-500'}`}
          >
            <ShoppingBag size={18} />
            <span className="text-[10px] mt-1">Orders</span>
          </button>

          <button 
            onClick={() => setActiveTab('employees')}
            className={`flex flex-col items-center text-xs ${activeTab === 'employees' ? 'text-emerald-400' : 'text-gray-500'}`}
          >
            <Users size={18} />
            <span className="text-[10px] mt-1">Employees</span>
          </button>
        </div>

      </div>
    </div>
  );
}
