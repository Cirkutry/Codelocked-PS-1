<script lang="ts">
  import { Github } from "@lucide/svelte";
</script>

<footer class="border-t mt-12 py-8">
  <div class="container mx-auto px-6 text-center text-sm text-muted-foreground flex flex-col items-center gap-2">
    <div>© {new Date().getFullYear()} Mars Habitat Resource Tracker</div>
    <div>Website made with ❤️ by Kre0lidge.</div>
    <a
      href="https://github.com/Cirkutry/Codelocked-PS-1"
      target="_blank"
      rel="noopener noreferrer"
      class="flex items-center gap-1 text-primary hover:underline"
    >
      <Github class="w-4 h-4" />
      GitHub Repo
    </a>
  </div>
</footer>
