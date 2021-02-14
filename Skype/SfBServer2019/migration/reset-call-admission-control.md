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
localization_priority: Normal
description: Se um pool de Front End herdado estiver hospedando o cac (controle de admissão de chamadas), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de remover o pool de Front-End herdado.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753293"
---
# <a name="reset-call-admission-control"></a>Redefinir o controle de admissão de chamada

Se um pool de Front End herdado estiver hospedando o cac (controle de admissão de chamadas), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de remover o pool de Front-End herdado.
  
### <a name="to-reset-cac"></a>Para redefinir o CAC

1. Abra o Construtor de Topologia.
    
2. Clique com o botão direito no nó do site e, em seguida, clique em **Editar propriedades**.
    
3. Em **Configuração de Controle de Admissão de Chamadas**, certifique-se de que a opção **Habilitar controle de admissão de chamadas** está selecionada. 
    
4. Em **Pool de Front-End** para executar o CAC (controle de admissão de chamadas), selecione o pool do Skype for Business Server 2019 que hospedará o CAC e clique em **OK.**
    
5. Publique a topologia.
    

