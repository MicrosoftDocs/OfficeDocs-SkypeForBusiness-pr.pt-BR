---
title: Redefinir o controle de admissão de chamada
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Se um pool de Front-End herdado estiver hospedando o controle de admissão de chamada (CAC), você deve mover a hospedagem cac para um pool Skype for Business Server 2019 antes de poder remover o pool de Front-End herdado.
ms.openlocfilehash: f660f14adfcdee64d9fa4c79e08393d4f0a0af2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583445"
---
# <a name="reset-call-admission-control"></a>Redefinir o controle de admissão de chamada

Se um pool de Front-End herdado estiver hospedando o controle de admissão de chamada (CAC), você deve mover a hospedagem cac para um pool Skype for Business Server 2019 antes de poder remover o pool de Front-End herdado.
  
### <a name="to-reset-cac"></a>Para redefinir o CAC

1. Abra o Construtor de Topologia.
    
2. Clique com o botão direito no nó do site e, em seguida, clique em **Editar propriedades**.
    
3. Em **Configuração de Controle de Admissão de Chamadas**, certifique-se de que a opção **Habilitar controle de admissão de chamadas** está selecionada. 
    
4. Em **Pool de Front-End para executar** o controle de admissão de chamada (CAC), selecione o pool Skype for Business Server 2019 que deve hospedar o CAC e clique em **OK**.
    
5. Publique a topologia.
    

