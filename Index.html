import React, { useState, useEffect } from 'react';
import { ChevronLeft, ChevronRight, Info } from 'lucide-react';

const HabitTracker = () => {
  const [currentDate, setCurrentDate] = useState(new Date());
  const [habits, setHabits] = useState({});
  const [showInfo, setShowInfo] = useState(false);

  useEffect(() => {
    const saved = localStorage.getItem('minimal-habit-data');
    if (saved) {
      try {
        setHabits(JSON.parse(saved));
      } catch (e) {
        console.error("Failed to parse habits", e);
      }
    }
  }, []);

  useEffect(() => {
    localStorage.setItem('minimal-habit-data', JSON.stringify(habits));
  }, [habits]);

  const daysInMonth = (year, month) => new Date(year, month + 1, 0).getDate();
  const firstDayOfMonth = (year, month) => new Date(year, month, 1).getDay();

  const year = currentDate.getFullYear();
  const month = currentDate.getMonth();
  const monthName = currentDate.toLocaleString('default', { month: 'long' });

  const handlePrevMonth = () => setCurrentDate(new Date(year, month - 1, 1));
  const handleNextMonth = () => setCurrentDate(new Date(year, month + 1, 1));

  const toggleDay = (day) => {
    const dateKey = `${year}-${String(month + 1).padStart(2, '0')}-${String(day).padStart(2, '0')}`;
    const currentStatus = habits[dateKey] || 'none';
    let nextStatus = currentStatus === 'none' ? 'done' : currentStatus === 'done' ? 'missed' : 'none';
    setHabits({ ...habits, [dateKey]: nextStatus });
  };

  const getStats = () => {
    const monthPrefix = `${year}-${String(month + 1).padStart(2, '0')}`;
    const monthKeys = Object.keys(habits).filter(key => key.startsWith(monthPrefix));
    return {
      doneCount: monthKeys.filter(key => habits[key] === 'done').length,
      missedCount: monthKeys.filter(key => habits[key] === 'missed').length
    };
  };

  const { doneCount, missedCount } = getStats();
  const totalDays = daysInMonth(year, month);
  const startOffset = firstDayOfMonth(year, month);
  const calendarDays = [];

  for (let i = 0; i < startOffset; i++) {
    calendarDays.push(<div key={`pad-${i}`} className="h-12 w-12 sm:h-16 sm:w-16"></div>);
  }

  for (let d = 1; d <= totalDays; d++) {
    const dateKey = `${year}-${String(month + 1).padStart(2, '0')}-${String(d).padStart(2, '0')}`;
    const status = habits[dateKey] || 'none';
    const isToday = new Date().toDateString() === new Date(year, month, d).toDateString();

    let bgColor = 'bg-gray-100/50 dark:bg-gray-800/50 hover:bg-gray-200 dark:hover:bg-gray-700';
    let textColor = 'text-gray-600 dark:text-gray-400';

    if (status === 'done') {
      bgColor = 'bg-emerald-500 hover:bg-emerald-600';
      textColor = 'text-white font-bold';
    } else if (status === 'missed') {
      bgColor = 'bg-rose-500 hover:bg-rose-600';
      textColor = 'text-white font-bold';
    }

    calendarDays.push(
      <button
        key={d}
        onClick={() => toggleDay(d)}
        className={`h-12 w-12 sm:h-16 sm:w-16 rounded-2xl transition-all duration-300 flex flex-col items-center justify-center relative active:scale-90 ${bgColor} ${textColor} ${isToday && status === 'none' ? 'ring-2 ring-blue-400' : ''}`}
      >
        <span className="text-sm sm:text-base">{d}</span>
      </button>
    );
  }

  return (
    <div className="min-h-screen bg-[#F8FAFC] dark:bg-[#0F172A] p-6 sm:p-10 font-rounded transition-colors duration-500" style={{ fontFamily: '"Quicksand", "Nunito", system-ui, sans-serif' }}>
      {/* Import Rounded Fonts */}
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700&display=swap');
      `}</style>

      <div className="max-w-md mx-auto">
        {/* Header - Aligned Left */}
        <header className="text-left mb-10 flex items-start justify-between">
          <div className="flex-1">
            <h1 className="text-4xl font-bold text-gray-900 dark:text-white tracking-tight leading-tight">
              Habits
            </h1>
            <p className="text-gray-400 dark:text-gray-500 text-sm mt-1 font-medium">
              Consistency is key.
            </p>
          </div>
          <button 
            onClick={() => setShowInfo(!showInfo)}
            className="mt-1 p-2.5 rounded-2xl bg-white dark:bg-gray-800 shadow-sm text-gray-400 hover:text-blue-500 transition-all border border-gray-100 dark:border-gray-700 active:scale-95"
          >
            <Info size={22} strokeWidth={2.5} />
          </button>
        </header>

        {showInfo && (
          <div className="mb-8 p-5 bg-white dark:bg-gray-800 rounded-3xl text-sm text-gray-600 dark:text-gray-300 shadow-sm border border-gray-100 dark:border-gray-700 animate-in fade-in slide-in-from-top-4">
            <div className="space-y-3 font-medium">
              <div className="flex items-center gap-3">
                <div className="w-2 h-2 rounded-full bg-emerald-500" />
                <span>Tap once: Habit complete</span>
              </div>
              <div className="flex items-center gap-3">
                <div className="w-2 h-2 rounded-full bg-rose-500" />
                <span>Tap again: Habit missed</span>
              </div>
              <div className="flex items-center gap-3">
                <div className="w-2 h-2 rounded-full bg-gray-300" />
                <span>Tap third: Reset day</span>
              </div>
            </div>
          </div>
        )}

        {/* Stats Section */}
        <div className="grid grid-cols-2 gap-5 mb-10">
          <div className="bg-emerald-50/50 dark:bg-emerald-500/10 p-5 rounded-[2rem] border border-emerald-100 dark:border-emerald-500/20">
            <p className="text-[10px] text-emerald-600 dark:text-emerald-400 uppercase font-black tracking-widest mb-1">Success</p>
            <p className="text-3xl font-bold text-emerald-700 dark:text-emerald-300">{doneCount}</p>
          </div>
          <div className="bg-rose-50/50 dark:bg-rose-500/10 p-5 rounded-[2rem] border border-rose-100 dark:border-rose-500/20">
            <p className="text-[10px] text-rose-600 dark:text-rose-400 uppercase font-black tracking-widest mb-1">Missed</p>
            <p className="text-3xl font-bold text-rose-700 dark:text-rose-300">{missedCount}</p>
          </div>
        </div>

        {/* Calendar Card */}
        <div className="bg-white dark:bg-gray-900 rounded-[2.5rem] shadow-[0_20px_50px_rgba(0,0,0,0.04)] dark:shadow-none p-7 border border-gray-50 dark:border-gray-800">
          
          <div className="flex items-center justify-between mb-8">
            <button onClick={handlePrevMonth} className="p-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-xl transition-all">
              <ChevronLeft className="text-gray-400" strokeWidth={3} />
            </button>
            <h2 className="text-lg font-bold text-gray-800 dark:text-gray-100">
              {monthName} <span className="text-gray-300 dark:text-gray-600 font-medium ml-1">{year}</span>
            </h2>
            <button onClick={handleNextMonth} className="p-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-xl transition-all">
              <ChevronRight className="text-gray-400" strokeWidth={3} />
            </button>
          </div>

          <div className="grid grid-cols-7 gap-3 mb-4">
            {['S', 'M', 'T', 'W', 'T', 'F', 'S'].map((day, i) => (
              <div key={i} className="text-center text-[10px] font-black text-gray-300 dark:text-gray-600">
                {day}
              </div>
            ))}
          </div>

          <div className="grid grid-cols-7 gap-3">
            {calendarDays}
          </div>
        </div>

        {/* Legend */}
        <div className="mt-10 flex justify-center gap-8 text-[11px] font-bold text-gray-400 dark:text-gray-600">
          <span className="flex items-center gap-2">
            <span className="w-1.5 h-1.5 rounded-full bg-emerald-500" /> DONE
          </span>
          <span className="flex items-center gap-2">
            <span className="w-1.5 h-1.5 rounded-full bg-rose-500" /> MISSED
          </span>
        </div>
      </div>
    </div>
  );
};

export default App = HabitTracker;


