---
title: Criar ou modificar um intervalo de números de Retirada de Chamada de Grupo Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Crie ou modifique um intervalo de números de Retirada de Chamada de Grupo Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 661efa69d7c7a3264872c4d83b94372d8d9951f1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738917"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Criar ou modificar um intervalo de números de Retirada de Chamada de Grupo Skype for Business

Crie ou modifique um intervalo de números de Retirada de Chamada de Grupo Skype for Business Server Enterprise Voice.

A Retirada de Chamada de Grupo se baseia no aplicativo Estacionamento de Chamada. Ao implantar a Coleta de Chamadas de Grupo, você deve configurar a tabela de órbita do estacionamento de chamadas com intervalos de números de telefone designados como números de grupo de retirada de chamadas. Esses números de grupo são os números que os usuários discam para atender chamadas que estão tocando para outro usuário.

Assim como os números de órbita do estacionamento de chamada, os números do grupo de retirada de chamadas precisam ser extensões virtuais que não tenham usuário ou telefone atribuídos a eles. Cada pool de Front-End onde você implanta a Coleta de Chamada de Grupo pode ter um ou mais intervalos de números de grupo de retirada de chamada. Os intervalos de número de grupo devem ser globalmente exclusivos em sua implantação e devem ser atribuídos como o **tipo GroupPickup.**

Use o procedimento a seguir para criar ou modificar um intervalo de números de grupo de retirada de chamada na tabela de órbita do estacionamento de chamada.

> [!NOTE]
> Você deve usar Skype for Business Server Shell de Gerenciamento para criar, modificar, remover e exibir intervalos de números de Retirada de Chamada de Grupo na tabela de órbita do estacionamento de chamada. Os intervalos de números de Retirada de Chamada de Grupo não estão disponíveis no Painel de Controle Skype for Business Server Grupo.

Os intervalos de número do grupo de retirada de chamada devem estar em conformidade com as seguintes regras:

- O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.

- O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.

- O intervalo de números deve ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

- Se o intervalo de números começar com o caractere \* ou #, o intervalo deverá ser maior que 100.

- Valores válidos: deve corresponder à cadeia de caracteres de expressão regular ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Isso significa que o valor deve ser uma cadeia de caracteres começando com o caractere ou # ou um \* número de 1 a 9 (o primeiro caractere não pode ser um zero). Se o primeiro caractere for ou #, o caractere a seguir deverá ser um \* número de 1 a 9 (não pode ser um zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", " \* 92000", " 95551212" e \* "915551212"). Se o primeiro caractere não for ou #, o primeiro caractere deverá ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um com um número de \* 0 a 9 (por exemplo, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para criar ou modificar um intervalo de grupo de retirada de chamada

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários** conforme descrito em Permissões de Instalação do Representante .

2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**

3. Use **New-CsCallParkOrbit** para criar um novo intervalo de números de grupo de retirada de chamadas. Use **Set-CsCallParkOrbit** para modificar um intervalo existente de números de retirada de chamadas.

    Na linha de comando, execute:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Por exemplo:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    O exemplo a seguir mostra como alterar um intervalo de números de órbitas de estacionamento de chamada para grupos de retirada de chamada.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Use este cmdlet para alterar o tipo atribuído a intervalos de números somente se você especificou inicialmente o tipo incorreto e o intervalo de grupo ainda não está em uso. Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o Estacionamento de Chamada ou a Retirada de Chamada de Grupo pararão de funcionar para esse intervalo de números. Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo Estacionamento de Chamadas não poderá mais usar esse intervalo de órbitas para estacionar chamadas.

## <a name="see-also"></a>Confira também

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Excluir um intervalo de órbita de estacionamento de chamada](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)