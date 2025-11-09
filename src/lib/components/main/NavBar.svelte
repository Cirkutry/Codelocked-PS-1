<script lang="ts">
  import * as NavigationMenu from "$lib/components/ui/navigation-menu";
  import { toggleMode } from "mode-watcher";
  import SunIcon from "@lucide/svelte/icons/sun";
  import MoonIcon from "@lucide/svelte/icons/moon";
  import logo from "$lib/assets/images/logo.png";
</script>

<header class="py-4 border-b border-border/40">
  <div class="container mx-auto px-6 flex items-center justify-between">
    <div class="flex items-center gap-3">
        <img
        src={logo}
        alt="Olympus Mons Base logo"
        class="h-14 w-14 object-contain"
        />
      <span class="text-xl font-semibold">Olympus Mons Base</span>
    </div>

    <NavigationMenu.Root>
      <NavigationMenu.List class="hidden sm:flex items-center gap-2">
        <NavigationMenu.Item>
          <NavigationMenu.Link href="/" class="px-3 py-2 rounded-md">
            Home
          </NavigationMenu.Link>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
          <NavigationMenu.Link href="#habitat-status" class="px-3 py-2 rounded-md">
            Status
          </NavigationMenu.Link>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
          <NavigationMenu.Link href="#log" class="px-3 py-2 rounded-md">
            Crew Log
          </NavigationMenu.Link>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
          <NavigationMenu.Link href="#environment" class="px-3 py-2 rounded-md">
            Environment
          </NavigationMenu.Link>
        </NavigationMenu.Item>

        <NavigationMenu.Item>
          <NavigationMenu.Link href="#archive" class="px-3 py-2 rounded-md">
            Archive
          </NavigationMenu.Link>
        </NavigationMenu.Item>

      </NavigationMenu.List>
    </NavigationMenu.Root>

    <button
      class="relative inline-flex items-center justify-center h-9 w-9 rounded-md border p-1"
      aria-label="Toggle theme"
      on:click={toggleMode}
    >
      <SunIcon class="h-[1.1rem] w-[1.1rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
      <MoonIcon class="absolute h-[1.1rem] w-[1.1rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
      <span class="sr-only">Toggle theme</span>
    </button>
  </div>
</header>
