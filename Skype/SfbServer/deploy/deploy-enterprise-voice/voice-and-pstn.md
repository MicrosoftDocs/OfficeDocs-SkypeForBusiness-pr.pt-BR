---
title: Configurar políticas de voz, registros de uso de PSTN e rotas de voz em Skype for Business
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Resumo: saiba como configurar políticas de voz, registros de uso PSTN e rotas de voz Skype for Business Server.'
ms.openlocfilehash: 62fcd557a0cdbaf8064e49f7c1c695f0f6f31880
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759053"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Configurar políticas de voz, registros de uso de PSTN e rotas de voz em Skype for Business
 
**Resumo:** Saiba como configurar políticas de voz, registros de uso PSTN e rotas de voz Skype for Business Server.
  
Políticas de voz, registros de uso PSTN e rotas de voz estão totalmente relacionados. Configure as políticas de voz selecionando um conjunto de recursos de chamada e, em seguida, atribuindo à política um conjunto de registros de uso da PSTN, que especificam quais direitos serão autorizados para os usuários ou grupos aos quais foi atribuída a política de voz. As rotas de voz também recebem registros de uso da PSTN, que servem para corresponder as rotas aos usuários que têm autorização para usá-las. Isto é, os usuários podem somente fazer chamadas que utilizem as rotas para as quais exista um registro de uso da PSTN correspondente.
  
O fluxo de trabalho recomendado para uma nova implantação Enterprise Voice é de começar configurando uma política de voz que inclua os registros de uso PSTN adequados e, então, associar as rotas apropriadas à cada registro de uso PSTN. 
  
> [!NOTE]
> Você também pode criar políticas de voz com  *escopo de*  usuário e atribuí-las a usuários ou grupos individuais.
  
Para as etapas detalhas para realizar cada uma destas tarefas, consulte os procedimentos nesta seção.
  
## <a name="in-this-section"></a>Nesta seção

- [Criar ou modificar uma política de voz e configurar registros de uso PSTN em Skype for Business](voice-policy-and-pstn-usage-records.md)
    
- [Configurar a saída de caixa postal no Skype for Business](configure-voice-mail-escape.md)
    
- [Exibir registros de uso de PSTN em Skype for Business](view-pstn-usage-records.md)
    
- [Criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md)
    
- [Exportar ou importar um arquivo de configuração de rota de voz no Skype for Business](voice-route-configuration-import-export.md)
    
- [Publicar alterações pendentes na configuração de roteamento de voz Skype for Business](voice-route-config-changes.md)
    

