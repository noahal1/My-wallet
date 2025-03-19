<script setup>
import americanBank from '@images/logos/american-bank.png'
import citiBank from '@images/logos/citi-bank.png'
import gumroad from '@images/logos/gumroad.png'
import mastercardLabel from '@images/logos/mastercard-label.png'
import stripe from '@images/logos/stripe.png'

const deposits = [
  {
    title: 'Gumroad Account',
    subtitle: 'Sell UI Kit',
    amount: '+$4,650',
    logo: gumroad,
  },
  {
    title: 'Mastercard',
    subtitle: 'Wallet deposit',
    amount: '+$92,705',
    logo: mastercardLabel,
  },
  {
    title: 'Stripe Account',
    subtitle: 'iOS Application',
    amount: '+$957',
    logo: stripe,
  },
  {
    title: 'American Bank',
    subtitle: 'American Bank',
    amount: '+$6,837',
    logo: americanBank,
  },
  {
    title: 'Bank Account',
    subtitle: 'Wallet deposit',
    amount: '+$8,934',
    logo: citiBank,
  },
]

const withdraws = [
  {
    title: '企业合作支出',
    subtitle: '技术解决方案',
    amount: '-$28,500',
  },
  {
    title: '项目奖金',
    subtitle: 'Q4季度奖金',
    amount: '-$15,200',
  },
]
</script>

<template>
  <VCard>
    <VRow no-gutters>
      <VCol
        cols="12"
        md="6"
      >
        <VCardItem>
          <VCardTitle>Deposit</VCardTitle>

          <template #append>
            <h6 class="text-h6">
              <a
                href="javascript:void(0)"
                class="text-primary"
              >View All</a>
            </h6>
          </template>
        </VCardItem>

        <VCardText>
          <VList class="card-list">
            <VListItem
              v-for="deposit in deposits"
              :key="deposit.logo"
            >
              <template #prepend>
                <div class="me-4">
                  <VImg
                    :height="30"
                    :width="30"
                    :src="deposit.logo"
                  />
                </div>
              </template>

              <VListItemTitle class="font-weight-medium mb-1">
                {{ deposit.title }}
              </VListItemTitle>
              <VListItemSubtitle class="text-body-1">
                {{ deposit.subtitle }}
              </VListItemSubtitle>

              <template #append>
                <VListItemAction class="text-success font-weight-medium">
                  {{ deposit.amount }}
                </VListItemAction>
              </template>
            </VListItem>
          </VList>
        </VCardText>
      </VCol>

      <VDivider :vertical="$vuetify.display.mdAndUp" />

      <VCol
        cols="12"
        md="6"
      >
        <VCardItem>
          <VCardTitle>Withdraw</VCardTitle>

          <template #append>
            <h6 class="text-h6">
              <a
                href="javascript:void(0)"
                class="text-primary"
              >View All</a>
            </h6>
          </template>
        </VCardItem>

        <VCardText>
          <VList class="card-list">
            <VListItem
              v-for="withdraw in withdraws"
              :key="withdraw.logo"
            >
              <template #prepend>
                <div class="me-4">
                  <VImg
                    :height="30"
                    :width="30"
                    :src="withdraw.logo"
                  />
                </div>
              </template>

              <VListItemTitle class="font-weight-medium mb-1">
                {{ withdraw.title }}
              </VListItemTitle>
              <VListItemSubtitle class="text-body-1">
                {{ withdraw.subtitle }}
              </VListItemSubtitle>
              <template #append>
                <VListItemAction>
                  <span class="text-error font-weight-medium">
                    {{ withdraw.amount }}
                  </span>
                </VListItemAction>
              </template>
            </VListItem>
          </VList>
        </VCardText>
      </VCol>
    </VRow>
  </VCard>
</template>

<style lang="scss" scoped>
.card-list {
--v-card-list-gap: 1.25rem;
}
</style>

