---
title: Redefinir controle de admissão de chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812799"
---
# <a name="reset-call-admission-control"></a>Redefinir controle de admissão de chamada

Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.
  
### <a name="to-reset-cac"></a>Para redefinir o CAC

1. Abrir o construtor de topologias.
    
2. Clique com o botão direito do mouse no nó do site e, em seguida, clique em **Editar propriedades**.
    
3. Em **configuração de controle de admissão de chamada**, verifique se a opção **habilitar controle de admissão de chamadas** está selecionada. 
    
4. Em **pool de front-ends para executar o controle de admissão de chamadas (CAC)**, selecione o pool do Skype for Business Server 2019 para hospedar o CAC e, em seguida, clique em **OK**.
    
5. Publique a topologia.
    

