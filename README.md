import { useState } from 'react';
import { Button } from "/components/ui/button";
import { Input } from "/components/ui/input";
import { Label } from "/components/ui/label";
import { Textarea } from "/components/ui/textarea";

export default function ChatGptAi() {
  const [prompt, setPrompt] = useState('');
  const [response, setResponse] = useState('');

  const handleSubmit = (event) => {
    event.preventDefault();
    const responseText = `This is a response to your prompt: ${prompt}`;
    setResponse(responseText);
  };

  return (
    <div className="max-w-md mx-auto p-4 space-y-4">
      <h1 className="text-3xl font-bold">ChatGPT AI</h1>
      <form onSubmit={handleSubmit}>
        <div className="space-y-2">
          <Label htmlFor="prompt">Enter your prompt:</Label>
          <Input id="prompt" value={prompt} onChange={(event) => setPrompt(event.target.value)} />
        </div>
        <Button type="submit">Submit</Button>
      </form>
      <div className="space-y-2">
        <Label>Response:</Label>
        <Textarea value={response} readOnly />
      </div>
    </div>
  );
}
