---
title: Redefinir controle de admissão de chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307095"
---
# <a name="reset-call-admission-control"></a>Redefinir controle de admissão de chamada

Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.
  
### <a name="to-reset-cac"></a>Para redefinir o CAC

1. Abrir o construtor de topologias.
    
2. Clique com o botão direito do mouse no nó do site e, em seguida, clique em **Editar propriedades**.
    
3. Em **configuração de controle de admissão de chamada**, verifique se a opção **habilitar controle de admissão de chamadas** está selecionada. 
    
4. Em **pool de front-ends para executar o controle de admissão de chamadas (CAC)**, selecione o pool do Skype for Business Server 2019 para hospedar o CAC e, em seguida, clique em **OK**.
    
5. Publique a topologia.
    

