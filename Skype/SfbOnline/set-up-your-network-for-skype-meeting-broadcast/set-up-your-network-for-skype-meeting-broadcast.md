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
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865155"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar a rede para a Transmissão de Reunião do Skype

Depois de [habilitar a Transmissão de](enable-skype-meeting-broadcast.md) Reunião do Skype, você precisa configurar sua rede. Faça esta etapa se quiser realizar webinars e outras transmissões para pessoas de fora da sua empresa.

> [!IMPORTANT]
> O Skype for Business Online se desposenta em 31 de julho de 2021, momento em que o acesso ao serviço terminará. Incentivamos os clientes a iniciar a atualização para o Microsoft Teams, o cliente principal para comunicações e trabalho em equipe no Microsoft 365.

Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.

Para ignorar esta etapa e, em vez disso, adicionar outra empresa à federação para que você possa convidá-las para transmissões, siga as etapas em Permitir que os usuários contatem usuários externos [do Skype for Business.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>Etapa 1: configurar domínios permitidos

Use **um** dos seguintes métodos para configurar domínios permitidos:

## #

 **Método 1: Usar o centro de administração**

1. Vá para o centro de administração e, em seguida, na barra de entrada à esquerda, clique em **Complementos** de Serviços de Configurações e escolha Skype for  >  **&amp;** **Business.**

2. Na página **Compartilhamento** externo em Exceções de **domínio,** selecione Todos os domínios são **bloqueados,** exceto, e insira os seguintes domínios, separados por uma vírgula (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Clique em **Salvar**.

## #

 **Método 2: Usar o Windows PowerShell**

- No **Menu Iniciar,** clique com o botão direito do mouse **no Windows PowerShell** e clique **em Executar como administrador.** Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Etapa 2: Adicionar domínios, URLs e endereços IP de Transmissão de Reunião do Skype

A segunda etapa no processo de configuração é primeiro adicionar domínios necessários e, em seguida, adicionar endereços IP e URLs necessários para que a Transmissão de Reunião do Skype funcione.

- **Adicione as URLs e endereços IP necessários** do ponto de extremidade do Skype for Business Online, vendo quais são necessários [aqui.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas

Se você tem uma organização do Skype for Business Online e uma implantação local do Lync Server 2010, do Microsoft Lync Server 2013 e do Skype for Business Server 2015 e tem usuários online e locais, há outras etapas de configuração que você precisará fazer além das anteriores para permitir que sua organização local se comunique com o Skype for Business Online e permita que todos os usuários insuportem a uma Transmissão de Reunião do Skype. Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Tópicos relacionados

[Habilitar a Transmissão de Reunião do Skype](enable-skype-meeting-broadcast.md)

[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



