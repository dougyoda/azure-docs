---
author: cherylmc
ms.author: cherylmc
ms.service: vpn-gateway
ms.topic: include
ms.date: 11/23/2021
---

1. Sign in to the [Azure portal](https://portal.azure.com).
1. In **Search resources, service, and docs (G+/)**, type ***virtual network***. Select **Virtual network** from the **Marketplace** results to open the **Virtual network** page.

   :::image type="content" source="./media/vpn-gateway-basic-vnet-rm-portal-include/marketplace-results.png" alt-text="Screenshot shows the Azure portal Search bar results and selecting Virtual Network from Marketplace." :::
1. On the **Virtual network** page, click **Create**. This opens the **Create virtual network** page.
1. On the **Basics** tab, configure the VNet settings for **Project details** and **Instance details**. You'll see a green check mark when the values you enter are validated. The values shown in the example can be adjusted according to the settings that you require.

   :::image type="content" source="./media/vpn-gateway-basic-vnet-rm-portal-include/basics.png" alt-text="Screenshot shows the Basics tab." :::

   - **Subscription**: Verify that the subscription listed is the correct one. You can change subscriptions by using the drop-down.
   - **Resource group**: Select an existing resource group, or click **Create new** to create a new one. For more information about resource groups, see [Azure Resource Manager overview](../articles/azure-resource-manager/management/overview.md#resource-groups).
   - **Name**: Enter the name for your virtual network.
   - **Region**: Select the location for your VNet. The location determines where the resources that you deploy to this VNet will live.
1. Click **IP Addresses** to advance to the IP Addresses tab. On the IP Addresses tab, configure the settings. The values shown in the example can be adjusted according to the settings that you require.

   :::image type="content" source="./media/vpn-gateway-basic-vnet-rm-portal-include/addresses.png" alt-text="Screenshot shows the IP Addresses tab." :::

   - **IPv4 address space**: By default, an address space is automatically created. You can click the address space to adjust it to reflect your own values. You can also add more address spaces.
   - **Subnet**: If you use the default address space, a default subnet is created automatically. If you change the address space, you need to add a subnet. Select **+ Add subnet** to open the **Add subnet** window. Configure the following settings and then select **Add** to add the values.
      - **Subnet name**: In this example, we named the subnet "FrontEnd".
      - **Subnet address range**: The address range for this subnet.

1. Click **Security** to advance to the Security tab. At this time, leave the default values.

   - **BastionHost**: Disable
   - **DDoS Protection Standard**: Disable
   - **Firewall**: Disable
1. Select **Review + create** to validate the virtual network settings.
1. After the settings have been validated, click **Create** to create the virtual network.
