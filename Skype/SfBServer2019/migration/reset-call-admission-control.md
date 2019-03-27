---
title: Redefinir controle de admissão de chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se um pool de Front-End herdado está hospedando o controle de admissão de chamadas (CAC), você deve mover a hospedagem de CAC para um Skype para Business Server 2019 pool antes de poder remover o pool de Front-End herdado.
ms.openlocfilehash: 3b94322b86feb2c647f88102617ab1dcc9d5f8bc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895772"
---
# <a name="reset-call-admission-control"></a>Redefinir controle de admissão de chamada

Se um pool de Front-End herdado está hospedando o controle de admissão de chamadas (CAC), você deve mover a hospedagem de CAC para um Skype para Business Server 2019 pool antes de poder remover o pool de Front-End herdado.
  
### <a name="to-reset-cac"></a>Para redefinir o CAC

1. Abra o construtor de topologia.
    
2. Com o botão direito no nó do site e, em seguida, clique em **Editar propriedades**.
    
3. Em **configuração de controle de admissão de chamada**, certifique-se de **Que Enable Call Admission Control** está selecionada. 
    
4. Em **pool de Front-End para executar o controle de admissão de chamadas (CAC)**, selecione o Skype para pool de negócios 2019 de servidor hospedar o CAC e, em seguida, clique em **Okey**.
    
5. Publique a topologia.
    

