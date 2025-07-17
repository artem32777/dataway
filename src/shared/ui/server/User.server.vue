<script setup>
import { withAccelerate } from '@prisma/extension-accelerate'

const prisma = usePrismaClient().$extends(withAccelerate())
const user = await prisma.user.findMany({
	where: { name: 'vasya777' },
})
</script>

<template>
	<div>
		{{ user ? user : 'No user has been added yet.' }}
	</div>
</template>
