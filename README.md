# HumoursHub
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs';
import JokeGenerator from '@/components/joke-generator';
import PunSuggester from '@/components/pun-suggester';
import { HumorHubLogo } from '@/components/icons';
import { Lightbulb, PartyPopper } from 'lucide-react';

export default function Home() {
  return (
    <div className="flex flex-col items-center min-h-dvh bg-background text-foreground p-4 sm:p-8">
      <header className="flex flex-col items-center text-center mb-8 w-full max-w-3xl">
        <HumorHubLogo className="w-24 h-24 mb-4 text-primary" />
        <h1 className="text-4xl md:text-5xl font-bold font-headline tracking-tight">
          Welcome to HumorHub
        </h1>
        <p className="mt-2 text-lg text-muted-foreground">
          Your one-stop-shop for AI-powered giggles and groans.
        </p>
      </header>

      <main className="w-full max-w-xl">
        <Tabs defaultValue="jokes" className="w-full">
          <TabsList className="grid w-full grid-cols-2 bg-muted/60">
            <TabsTrigger value="jokes" className="gap-2">
              <PartyPopper className="w-4 h-4" /> Joke Generator
            </TabsTrigger>
            <TabsTrigger value="puns" className="gap-2">
              <Lightbulb className="w-4 h-4" /> Pun Suggester
            </TabsTrigger>
          </TabsList>
          <TabsContent value="jokes" className="mt-6">
            <JokeGenerator />
          </TabsContent>
          <TabsContent value="puns" className="mt-6">
            <PunSuggester />
          </TabsContent>
        </Tabs>
      </main>
      <footer className="text-center mt-auto pt-8 text-muted-foreground text-sm">
        <p>
          Built with creativity by an expert user experience designer.
        </p>
      </footer>
    </div>
  );
}

