<script lang="ts">
  import Triangle from "lucide-svelte/icons/triangle";
  import Bot from "lucide-svelte/icons/bot";
  import SquareTerminal from "lucide-svelte/icons/square-terminal";
  import CodeXML from "lucide-svelte/icons/code-xml";
  import Settings2 from "lucide-svelte/icons/settings-2";
  import LifeBuoy from "lucide-svelte/icons/life-buoy";
  import Book from "lucide-svelte/icons/book";
  import SquareUser from "lucide-svelte/icons/square-user";
  import Settings from "lucide-svelte/icons/settings";
  import Rabbit from "lucide-svelte/icons/rabbit";
  import Bird from "lucide-svelte/icons/bird";
  import Turtle from "lucide-svelte/icons/turtle";

  import Paperclip from "lucide-svelte/icons/paperclip";

  import CornerDownLeft from "lucide-svelte/icons/corner-down-left";

  import { Badge } from "$lib/components/ui/badge/index.js";
  import { Button } from "$lib/components/ui/button/index.js";

  import { Input } from "$lib/components/ui/input/index.js";
  import { Textarea } from "$lib/components/ui/textarea/index.js";
  import { Label } from "$lib/components/ui/label/index.js";
  import * as Select from "$lib/components/ui/select/index.js";
</script>

<div class="grid h-full w-full pl-[53px]">
  <div class="flex flex-col">
    <main
      class="grid flex-1 gap-4 overflow-auto p-4 md:grid-cols-2 lg:grid-cols-3"
    >
      <div class="relative hidden flex-col items-start gap-8 md:flex">
        <form class="grid w-full items-start gap-6">
          <fieldset class="grid gap-6 rounded-lg border p-4">
            <legend class="-ml-1 px-1 text-sm font-medium"> Settings </legend>
            <div class="grid gap-3">
              <Label for="model">Model</Label>
              <!-- <Select.Root>
                <Select.Trigger
                  id="model"
                  class="items-start [&_[data-description]]:hidden"
                >
                  <Select.Value placeholder="Select a model" />
                </Select.Trigger>
                <Select.Content>
                  <Select.Item value="genesis" label="Neural Genesis">
                    <div class="text-muted-foreground flex items-start gap-3">
                      <Rabbit class="size-5" />
                      <div class="grid gap-0.5">
                        <p>
                          Neural
                          <span class="text-foreground font-medium">
                            Genesis
                          </span>
                        </p>
                        <p class="text-xs" data-description>
                          Our fastest model for general use cases.
                        </p>
                      </div>
                    </div>
                  </Select.Item>
                  <Select.Item value="explorer" label="Neural Explorer">
                    <div class="text-muted-foreground flex items-start gap-3">
                      <Bird class="size-5" />
                      <div class="grid gap-0.5">
                        <p>
                          Neural
                          <span class="text-foreground font-medium">
                            Explorer
                          </span>
                        </p>
                        <p class="text-xs" data-description>
                          Performance and speed for efficiency.
                        </p>
                      </div>
                    </div>
                  </Select.Item>
                  <Select.Item value="quantum">
                    <div class="text-muted-foreground flex items-start gap-3">
                      <Turtle class="size-5" />
                      <div class="grid gap-0.5">
                        <p>
                          Neural
                          <span class="text-foreground font-medium">
                            Quantum
                          </span>
                        </p>
                        <p class="text-xs" data-description>
                          The most powerful model for complex computations.
                        </p>
                      </div>
                    </div>
                  </Select.Item>
                </Select.Content>
              </Select.Root> -->
            </div>
            <div class="grid gap-3">
              <Label for="temperature">Temperature</Label>
              <Input id="temperature" type="number" placeholder="0.4" />
            </div>
            <div class="grid grid-cols-2 gap-4">
              <div class="grid gap-3">
                <Label for="top-p">Top P</Label>
                <Input id="top-p" type="number" placeholder="0.7" />
              </div>
              <div class="grid gap-3">
                <Label for="top-k">Top K</Label>
                <Input id="top-k" type="number" placeholder="0.0" />
              </div>
            </div>
          </fieldset>
          <fieldset class="grid gap-6 rounded-lg border p-4">
            <legend class="-ml-1 px-1 text-sm font-medium"> Messages </legend>
            <div class="grid gap-3">
              <Label for="role">Role</Label>
              <!-- <Select.Root selected={{ value: "system", label: "System" }}>
                <Select.Trigger>
                  <Select.Value placeholder="Select a role" />
                </Select.Trigger>
                <Select.Content>
                  <Select.Item value="system">System</Select.Item>
                  <Select.Item value="user">User</Select.Item>
                  <Select.Item value="assistant">Assistant</Select.Item>
                </Select.Content>
              </Select.Root> -->
            </div>
            <div class="grid gap-3">
              <Label for="content">Content</Label>
              <Textarea
                id="content"
                placeholder="You are a..."
                class="min-h-[9.5rem]"
              />
            </div>
          </fieldset>
        </form>
      </div>
      <div
        class="bg-muted/50 relative flex h-full min-h-[50vh] flex-col rounded-xl p-4 lg:col-span-2"
      >
        <Badge variant="outline" class="absolute right-3 top-3">Output</Badge>
        <div class="flex-1" />
        <form
          class="bg-background focus-within:ring-ring relative overflow-hidden rounded-lg border focus-within:ring-1"
        >
          <Label for="message" class="sr-only">Message</Label>
          <Textarea
            id="message"
            placeholder="Type your message here..."
            class="min-h-12 resize-none border-0 p-3 shadow-none focus-visible:ring-0"
          />
          <div class="flex items-center p-3 pt-0">
            <Button type="button" size="sm" class="ml-auto gap-1.5">
              Send Message
              <CornerDownLeft class="size-3.5" />
            </Button>
          </div>
        </form>
      </div>
    </main>
  </div>
</div>
