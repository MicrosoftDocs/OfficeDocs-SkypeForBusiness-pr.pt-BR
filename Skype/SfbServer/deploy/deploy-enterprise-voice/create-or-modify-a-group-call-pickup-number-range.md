---
title: Criar ou modificar um intervalo de números de Atendimento de Chamadas em Grupo no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Criar ou modificar um intervalo de números de Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822401"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Criar ou modificar um intervalo de números de Atendimento de Chamadas em Grupo no Skype for Business

Criar ou modificar um intervalo de números de Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice.

O Atendimento de Chamada em Grupo é baseado no aplicativo Estacionamento de Chamada. Ao implantar o Atendimento de Chamadas em Grupo, você deve configurar a tabela de órbita de estacionamento de chamadas com intervalos de números de telefone designados como números de grupo de atendimento de chamadas. Esses números de grupo são os números que os usuários discam para atender chamadas que estão tocando para outro usuário.

Como os números de órbita de estacionamento de chamada, os números do grupo de atendimento de chamadas precisam ser ramais virtuais que não têm nenhum usuário ou telefone atribuído a eles. Cada pool de Front End onde você implanta o Atendimento de Chamada em Grupo pode ter um ou mais intervalos de números de grupo de atendimento de chamada. Os intervalos de números de grupo devem ser globalmente exclusivos em sua implantação e devem ser atribuídos como o tipo **GroupPickup.**

Use o procedimento a seguir para criar ou modificar um intervalo de números de grupo de atendimento de chamada na tabela de órbita de estacionamento de chamada.

> [!NOTE]
> Você deve usar o Shell de Gerenciamento do Skype for Business Server para criar, modificar, remover e exibir intervalos de números de Atendimento de Chamadas em Grupo na tabela de órbita de estacionamento de chamadas. Os intervalos de números de Atendimento de Chamadas em Grupo não estão disponíveis no Painel de Controle do Skype for Business Server.

Os intervalos de números do grupo de atendimento de chamada devem estar em conformidade com as seguintes regras:

- O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.

- O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.

- O intervalo de números deve ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

- Se o intervalo de números começar com o caractere \* ou #, o intervalo deverá ser maior que 100.

- Valores válidos: devem corresponder à cadeia de caracteres de expressão regular ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Isso significa que o valor deve ser uma cadeia de caracteres começando com o caractere ou # ou um número de 1 a 9 (o primeiro caractere \* não pode ser zero). Se o primeiro caractere for ou #, o caractere seguinte deverá ser um número \* de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", " \* 92000", " \* 95551212" e "915551212"). Se o primeiro caractere não for ou #, o primeiro caractere deverá ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um com um número de \* 0 a 9 (por exemplo, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para criar ou modificar um intervalo de grupo de atendimento de chamada

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

3. Use **New-CsCallParkOrbit para** criar um novo intervalo de números de grupo de atendimento de chamadas. Use **Set-CsCallParkOrbit para** modificar um intervalo existente de números de atendimento de chamadas.

    Na linha de comando, execute:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Por exemplo:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    O exemplo a seguir mostra como alterar um intervalo de números de órbitas de estacionamento de chamada para grupos de atendimento de chamada.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Use este cmdlet para alterar o tipo atribuído a intervalos de números somente se você tiver especificado inicialmente o tipo incorreto e o intervalo de grupo ainda não estiver em uso. Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o Estacionamento de Chamada ou o Atendimento de Chamada em Grupo deixarão de funcionar para esse intervalo de números. Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo Estacionamento de Chamadas não poderá mais usar esse intervalo de órbitas para estacionar chamadas.

## <a name="see-also"></a>Confira também

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Excluir um intervalo de órbita de estacionamento de chamada](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
