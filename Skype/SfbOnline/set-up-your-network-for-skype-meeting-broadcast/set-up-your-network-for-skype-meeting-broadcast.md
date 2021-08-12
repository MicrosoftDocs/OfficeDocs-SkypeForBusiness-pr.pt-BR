---
title: Configurar a rede para a Transmissão de Reunião do Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 068ff156badaff9231f6e477e2f41668ea8f99fd26531f2a08155c4ee4763c05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308022"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar a rede para a Transmissão de Reunião do Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Depois de [habilitar Reunião do Skype transmissão Reunião do Skype](enable-skype-meeting-broadcast.md) transmissão, você precisará configurar sua rede. Faça esta etapa se quiser manter webinars e outras transmissões para pessoas fora da sua empresa.

> [!IMPORTANT]
> Skype for Business Online está se retirando em 31 de julho de 2021, quando o acesso ao serviço terminará. Incentivamos os clientes a começar a atualização para Microsoft Teams, o cliente principal para comunicações e trabalho em equipe Microsoft 365.

Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.

Para ignorar essa etapa e, em vez disso, adicionar outra empresa à sua federação para que você possa convidá-los para transmissões, siga as etapas em Permitir que os usuários contatem usuários externos Skype for Business [usuários](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Etapa 1: Configurar domínios permitidos

Use **um** dos seguintes métodos para configurar domínios permitidos:

### <a name="method-1-use-the-admin-center"></a>Método 1: Usar o centro de administração

1. Vá para o centro de administração e, na nav esquerda, clique em Configurações de serviços e escolha  >  **&amp;** **Skype for Business**.

2. Na página **compartilhamento** externo em **Exceções** de domínio, selecione Todos os domínios são **bloqueados,** exceto , e insira os domínios a seguir, separados com uma vírgula (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Clique em **Salvar**.

### <a name="method-2-use-windows-powershell"></a>Método 2: use Windows PowerShell

- No **Menu Iniciar,** clique com o botão direito **do mouse Windows PowerShell** clique em Executar como **administrador**. Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Etapa 2: Adicionar Reunião do Skype de transmissão, URLs e endereços IP

A segunda etapa no processo de instalação é primeiro adicionar domínios necessários e, em seguida, adicionar endereços IP e URLs que são necessárias para que Reunião do Skype Transmissão funcione.

- **Adicione as URLs** e endereços IP do ponto de extremidade Skype for Business online, vendo quais são necessários [aqui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas

Se você tiver uma organização do Skype for Business Online e uma implantação local do Lync Server 2010, do Microsoft Lync Server 2013 e do Skype for Business Server 2015 e tiver usuários online e no local, há outras etapas de instalação que você precisará fazer além das acima para permitir que sua organização local se comunique com o Skype for Business Online e permitir que todos os usuários insuportem uma transmissão Reunião do Skype. Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).

## <a name="related-topics"></a>Tópicos relacionados

[Habilitar a Transmissão de Reunião do Skype](enable-skype-meeting-broadcast.md)

[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
