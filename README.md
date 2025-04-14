import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { useState } from "react";

export default function Home() {
  const [showTeacher, setShowTeacher] = useState(false);

  const handleLogin = () => {
    const pw = window.prompt("Voer het wachtwoord in:");
    if (pw === "geheim123") {
      setShowTeacher(true);
    } else {
      alert("Wachtwoord onjuist");
    }
  };

  return (
    <div className="p-6 space-y-8">
      <h1 className="text-3xl font-bold">Lesmateriaal PAV & NCZ</h1>

      <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
        {/* PAV */}
        <Card>
          <CardContent className="p-4 space-y-3">
            <h2 className="text-xl font-semibold">📘 PAV</h2>
            <Button asChild><a href="https://1drv.ms/f/c/ae0c1f8043d70d03/EgEz6ecyRyZCgD7SJBGmoIcBKrvz3w5v1TNOUNW-aTIRKA?e=Rnk5V7" target="_blank">Bekijk materiaal (OneDrive)</a></Button>
            <Button asChild><a href="https://drive.proton.me/urls/6925FBFQ1C#iaYSroxmvzjQ" target="_blank">Bekijk materiaal (Proton Drive)</a></Button>
            <div className="pt-2">
              <h3 className="font-medium">🎯 Online oefeningen</h3>
              <iframe src="https://www.bookwidgets.com/play/BDJ9C7?teacher_id=6741049993267200" width="100%" height="400" frameBorder="0" allowFullScreen></iframe>
            </div>
          </CardContent>
        </Card>

        {/* NCZ */}
        <Card>
          <CardContent className="p-4 space-y-3">
            <h2 className="text-xl font-semibold">📗 NCZ</h2>
            <Button asChild><a href="https://1drv.ms/f/c/ae0c1f8043d70d03/Evj2ieG5HOhPtD9IN3NZ-M8Bsr0VkIJylyoOmav8U2n4JQ?e=FpMX4Q" target="_blank">Bekijk materiaal (OneDrive)</a></Button>
            <Button asChild><a href="https://drive.proton.me/urls/WQQF0QWKP4#SJ3cnG6TnRL9" target="_blank">Bekijk materiaal (Proton Drive)</a></Button>
            <div className="pt-2">
              <h3 className="font-medium">🎯 Online oefeningen</h3>
              <p className="text-muted-foreground">(BookWidgets komen hier binnenkort)</p>
            </div>
          </CardContent>
        </Card>

        {/* Chattie */}
        <Card className="md:col-span-2">
          <CardContent className="p-4 space-y-3">
            <h2 className="text-xl font-semibold">🤖 Chattie de Chatbot</h2>
            <p>Chattie is een educatieve chatbot die ondersteuning kan bieden bij zowel PAV als NCZ.</p>
            <Button asChild><a href="https://jonateniers.github.io/chattie-de-chatbot/" target="_blank">Bezoek Chattie</a></Button>
          </CardContent>
        </Card>

        {/* Planning */}
        <Card className="md:col-span-2">
          <CardContent className="p-4 space-y-3">
            <h2 className="text-xl font-semibold">📅 Planning & Kalender</h2>
            <iframe src="https://calendar.google.com/calendar/embed?src=your_calendar_id&ctz=Europe%2FBrussels" style={{ border: 0 }} width="100%" height="600" frameBorder="0" scrolling="no"></iframe>
            <p className="text-sm text-muted-foreground">Gebruik Google Calendar of een andere planningstool om belangrijke lesmomenten te tonen.</p>
          </CardContent>
        </Card>

        {/* Toekomstige ideeën */}
        <Card className="md:col-span-2">
          <CardContent className="p-4 space-y-3">
            <h2 className="text-xl font-semibold">🚀 Toekomstige functies</h2>
            <ul className="list-disc list-inside space-y-1">
              <li>🧩 Interactieve elementen of mini-games integreren</li>
              <li>📥 Mogelijkheid voor leerlingen om opdrachten in te dienen</li>
              <li>🧾 Automatisch bundels genereren (bv. leerlingversie als PDF)</li>
              <li>🧠 Persoonlijke leerdoelen of voortgangsindicatoren</li>
            </ul>
            <p className="text-sm text-muted-foreground">Laat me weten welke jij eerst wil activeren!</p>
          </CardContent>
        </Card>
      </div>

      {/* Lerarenhoekje */}
      <div className="pt-8">
        <h2 className="text-2xl font-semibold">🔐 Lerarenhoekje</h2>
        {!showTeacher ? (
          <Button onClick={handleLogin}>Toegang aanvragen</Button>
        ) : (
          <Card className="mt-4">
            <CardContent className="p-4 space-y-3">
              <h3 className="text-xl font-semibold">📁 Lerarenmateriaal</h3>
              <ul className="list-disc list-inside space-y-1">
                <li><a href="https://drive.proton.me/urls/WQQF0QWKP4#SJ3cnG6TnRL9" target="_blank" className="text-blue-600 underline">Correctiesleutels & toetsen (NCZ)</a></li>
                <li><a href="https://drive.proton.me/urls/6925FBFQ1C#iaYSroxmvzjQ" target="_blank" className="text-blue-600 underline">Correctiesleutels & toetsen (PAV)</a></li>
                <li><a href="https://1drv.ms/f/c/ae0c1f8043d70d03/Evj2ieG5HOhPtD9IN3NZ-M8Bsr0VkIJylyoOmav8U2n4JQ?e=FpMX4Q" target="_blank" className="text-blue-600 underline">Extra leraardocumenten (OneDrive)</a></li>
              </ul>
              <p className="text-sm text-muted-foreground">Je hebt toegang. Deze zone kan nog uitgebreid worden met uploads of verborgen lessen.</p>
            </CardContent>
          </Card>
        )}
      </div>
    </div>
  );
}
