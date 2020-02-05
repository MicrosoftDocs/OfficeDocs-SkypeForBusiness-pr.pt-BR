---
title: Criar ou modificar um intervalo de números de tira de chamada em grupo no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Criar ou modificar um intervalo de números de retirada de chamadas em grupo no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 98fc59f12165e6299fafc5ed79797e6d25d151e3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767874"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Criar ou modificar um intervalo de números de tira de chamada em grupo no Skype for Business

Criar ou modificar um intervalo de números de retirada de chamadas em grupo no Skype for Business Server Enterprise Voice.

O recebimento de chamadas em grupo é baseado no aplicativo parque de chamadas. Ao implantar o recurso de recebimento de chamadas em grupo, você deve configurar a tabela órbita do estacionamento de chamada com intervalos de números de telefone designados como números de grupo de retirada de chamadas. Esses números do grupo são aqueles que os usuários discam para receber chamadas que estão tocando para outro usuário.

Como os números da órbita de estacionamento de chamada, os números do grupo de recebimento de chamada precisam ser extensões virtuais, sem nenhum usuário ou telefone atribuído. Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamadas. Os intervalos de números do grupo devem ser globalmente exclusivos em sua implantação e devem ser atribuídos como o tipo **GroupPickup**.

Utilize o procedimento a seguir para criar ou modificar o intervalo de números de um grupo de atendimento de chamadas na tabela de órbita de estacionamento de chamadas.

> [!NOTE]
> Você deve usar o Shell de gerenciamento do Skype for Business Server para criar, modificar, remover e exibir os intervalos de números de recebimento de chamadas em grupo na tabela órbita do estacionamento de chamadas. Os intervalos de números de retirada de chamadas em grupo não estão disponíveis no painel de controle do Skype for Business Server.

Os intervalos de números de grupo de atendimento de chamadas precisam estar de acordo com as regras a seguir:

- O número inicial do intervalo deve ser menor ou igual ao número final.

- O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.

- O intervalo de números precisa ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

- Se o intervalo de números começar com o \* caractere ou #, o intervalo deve ser maior que 100.

- Valores válidos: devem corresponder à cadeia de caracteres de expressão\\regular ([* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres que comece \* com o caractere ou # ou um número de 1 a 9 (o primeiro caractere não pode ser zero). Se o primeiro caractere for \* ou #, o seguinte caractere deve ser um número de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000"\*, "92000"\*, "95551212" e "915551212"). Se o primeiro caractere não \* for ou #, o primeiro caractere deve ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um dos números de 0 a 9 (por exemplo, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para criar ou modificar um intervalo de grupo de atendimento de chamadas

1. Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

3. Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de grupo de atendimento de chamadas. Use o **Set-CsCallParkOrbit** para modificar um intervalo existente de números de atendimento de chamadas.

    Na linha de comando, execute:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Por exemplo:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    O exemplo a seguir mostra como trocar um intervalo de números de órbitas de estacionamento de chamadas para grupos de atendimento de chamadas.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Use esse cmdlet para mudar o tipo atribuído aos intervalos de números somente se você tiver especificado inicialmente o tipo incorreto e somente caso o intervalo de grupo ainda não esteja em uso. Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o estacionamento de chamada ou o atendimento de chamada em grupo irá parar de funcionar para aquele intervalo de números. Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo de estacionamento de chamadas não poderá mais usar esse intervalo de órbitas para estacionar chamadas.

## <a name="see-also"></a>Confira também

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Excluir uma faixa de opções de estacionamento de chamada](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
