---
title: Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: d73b3e72aa7cd5f733406c861d8a3357fe28fe45
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883950"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para negócios

Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.

Atendimento de chamada do grupo é baseado no aplicativo de estacionamento de chamadas. Quando você implanta o atendimento de chamada de grupo, você deve configurar a tabela de órbita de estacionamento de chamada com intervalos de números de telefone são designados como números de retirada de grupo de chamada. Esses números do grupo são aqueles que os usuários discam para receber chamadas que estão tocando para outro usuário.

Como os números da órbita de estacionamento de chamada, os números do grupo de recebimento de chamada precisam ser extensões virtuais, sem nenhum usuário ou telefone atribuído. Cada pool de Front-End, onde você implanta o atendimento de chamada do grupo pode ter um ou mais intervalos de números de retirada de grupo de chamada. Os intervalos de números do grupo devem ser globalmente exclusivos em sua implantação e devem ser atribuídos como o tipo **GroupPickup**.

Utilize o procedimento a seguir para criar ou modificar o intervalo de números de um grupo de atendimento de chamadas na tabela de órbita de estacionamento de chamadas.

> [!NOTE]
> Você deve usar o Skype para Business Server Management Shell para criar, modificar, remover e exibir os intervalos de números de atendimento de chamada de grupo na tabela de órbita de estacionamento de chamada. Intervalos de números de atendimento de chamada de grupo não estão disponíveis no Skype para painel de controle do servidor de negócios.

Os intervalos de números de grupo de atendimento de chamadas precisam estar de acordo com as regras a seguir:

- O número inicial do intervalo deve ser menor ou igual ao número final.

- O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.

- O intervalo de números precisa ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

- Se o intervalo de números começa com o caractere \* ou #, o intervalo deve ser maior que 100.

- Valores válidos: deve coincidir com a cadeia de caracteres de expressão regular ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres iniciada com o caractere \* ou #, ou um número entre 1 e 9 (o primeiro caractere não pode ser um zero). Se o primeiro caractere for \* ou #, o caractere seguinte deve ser um número entre 1 e 9 (ele não pode ser um zero). Os caracteres subsequentes podem ser qualquer número entre 0 e 9 até sete caracteres adicionais (por exemplo, "#6000", "\*92000", "\*95551212" e "915551212"). Se o primeiro caractere não for \* ou #, o primeiro caractere deve ser um número entre 1 e 9 (ele não pode ser zero), seguido por até oito caracteres, cada um número entre 0 e 9 (por exemplo, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para criar ou modificar um intervalo de grupo de atendimento de chamadas

1. Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

3. Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de retirada de grupo de chamada. Use o **Set-CsCallParkOrbit** para modificar um intervalo existente de números de retirada de chamada.

    Na linha de comando, execute:

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Por exemplo:

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    O exemplo a seguir mostra como trocar um intervalo de números de órbitas de estacionamento de chamadas para grupos de atendimento de chamadas.

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Use esse cmdlet para mudar o tipo atribuído aos intervalos de números somente se você tiver especificado inicialmente o tipo incorreto e somente caso o intervalo de grupo ainda não esteja em uso. Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o estacionamento de chamada ou o atendimento de chamada em grupo irá parar de funcionar para aquele intervalo de números. Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo de estacionamento de chamada não pode usar aquele intervalo de Órbitas para estacionar chamadas.

## <a name="see-also"></a>Consulte também

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Excluir um intervalo de órbita de estacionamento de chamada](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)