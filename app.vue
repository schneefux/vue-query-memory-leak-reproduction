<template>
  <div>
    <NuxtWelcome />
  </div>
</template>

<script setup lang="ts">
import { onServerPrefetch } from "vue";
import { useQuery } from "@tanstack/vue-query";

const fetcher = async () => 'memory-leak'

const { suspense } = useQuery({ queryKey: ["test"], queryFn: fetcher });

onServerPrefetch(suspense);
</script>
