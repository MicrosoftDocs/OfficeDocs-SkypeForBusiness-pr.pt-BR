---
title: Configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Resumo: Saiba como configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para Business Server.'
ms.openlocfilehash: feb240600c02da2cdb5cabf9db8ca55605240901
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891277"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para negócios
 
**Resumo:** Saiba como configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para Business Server.
  
Políticas de voz, registros de uso PSTN e rotas de voz estão totalmente relacionados. Configure as políticas de voz selecionando um conjunto de recursos de chamada e, em seguida, atribuindo à política um conjunto de registros de uso da PSTN, que especificam quais direitos serão autorizados para os usuários ou grupos aos quais foi atribuída a política de voz. As rotas de voz também recebem registros de uso da PSTN, que servem para corresponder as rotas aos usuários que têm autorização para usá-las. Isto é, os usuários podem somente fazer chamadas que utilizem as rotas para as quais exista um registro de uso da PSTN correspondente.
  
O fluxo de trabalho recomendado para uma nova implantação Enterprise Voice é de começar configurando uma política de voz que inclua os registros de uso PSTN adequados e, então, associar as rotas apropriadas à cada registro de uso PSTN. 
  
> [!NOTE]
> Você também pode criar políticas de voz com escopo de *usuário* e atribuí-las aos usuários ou grupos individuais.
  
Para as etapas detalhas para realizar cada uma destas tarefas, consulte os procedimentos nesta seção.
  
## <a name="in-this-section"></a>Nesta seção

- [Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios](voice-policy-and-pstn-usage-records.md)
    
- [Configurar escape da caixa postal no Skype para negócios](configure-voice-mail-escape.md)
    
- [Exibir registros de uso PSTN em Skype para negócios](view-pstn-usage-records.md)
    
- [Criar ou modificar uma rota de voz no Skype para negócios](create-or-modify-a-voice-route.md)
    
- [Exportar ou importar um arquivo de configuração de rota de voz no Skype para negócios](voice-route-configuration-import-export.md)
    
- [Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md)
    

