import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";
import { Check } from "lucide-react";

const plano = {
  "Café da Manhã": [
    "Iogurte proteico + aveia + banana + chia/linhaça + café preto",
    "Shake de whey + castanhas + fruta (maçã ou banana)"
  ],
  "Lanche da Manhã": [
    "Fruta + queijo branco",
    "Fruta + ovo cozido"
  ],
  "Almoço": [
    "Proteína magra + carboidrato complexo + legumes/verduras + azeite"
  ],
  "Lanche da Tarde": [
    "Iogurte + aveia ou granola",
    "2 ovos cozidos + fruta",
    "Barrinha de proteína (≤5g açúcar)"
  ],
  "Pós-Treino": [
    "Whey + banana",
    "Omelete + legumes + pão integral"
  ],
  "Jantar": [
    "Sopa de legumes + frango desfiado",
    "Salada completa + azeite",
    "Omelete + legumes refogados"
  ]
};

export default function PlanoAlimentarApp() {
  const [checklist, setChecklist] = useState({});

  const toggleCheck = (refeicao, index) => {
    const key = `${refeicao}-${index}`;
    setChecklist((prev) => ({ ...prev, [key]: !prev[key] }));
  };

  return (
    <div className="p-4 max-w-xl mx-auto">
      <h1 className="text-2xl font-bold mb-4">Plano Alimentar Diário</h1>
      <Tabs defaultValue="Café da Manhã" className="w-full">
        <TabsList className="flex flex-wrap gap-2">
          {Object.keys(plano).map((refeicao) => (
            <TabsTrigger key={refeicao} value={refeicao}>
              {refeicao}
            </TabsTrigger>
          ))}
        </TabsList>
        {Object.entries(plano).map(([refeicao, opcoes]) => (
          <TabsContent key={refeicao} value={refeicao}>
            {opcoes.map((opcao, index) => (
              <Card
                key={index}
                onClick={() => toggleCheck(refeicao, index)}
                className={`my-2 cursor-pointer transition-all ${
                  checklist[`${refeicao}-${index}`] ? "border-green-500 bg-green-50" : ""
                }`}
              >
                <CardContent className="p-4 flex items-center justify-between">
                  <span>{opcao}</span>
                  {checklist[`${refeicao}-${index}`] && <Check className="text-green-600" />}
                </CardContent>
              </Card>
            ))}
          </TabsContent>
        ))}
      </Tabs>
    </div>
  );
}
