---
title: Skype for Business compatibilidade com Office aplicativos
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Entenda as maneiras como você pode acessar Skype for Business recursos de Outlook e outros Microsoft Office aplicativos.
ms.openlocfilehash: 06a019416ad8d32b0234b08c01b09630dd07a2ef
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862128"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business compatibilidade com Office aplicativos
 
Entenda as maneiras como você pode acessar Skype for Business recursos de Outlook e outros Microsoft Office aplicativos.
  
Este tópico descreve a compatibilidade do Skype for Business com várias versões de Microsoft Office suites. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype for Business

A tabela a seguir descreve os recursos Skype for Business que são suportados por várias versões do Office depois que o Exchange é implantado e integrado, conforme descrito em Integrar Skype for Business Server com [Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype for Business e Microsoft Office Compatibilidade**

|**Característica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|**Office 2016 para Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook recursos** ||||
|Personalizar Outlook de reunião (adicionar logotipo, URL de ajuda, aviso de isenção de responsabilidade, texto do rodapé)  |Não  |Sim   |Sim|
|Configurar a opção de reunião para silenciar áudio e vídeo do participante por padrão    |Não    |Sim    |Não    |
|Unified Contact Store for managing Contacts lists across Office and Skype for Business    |Não    |Sim (requer Exchange 2013 ou posterior)    |Sim    |
|Imagens de perfil de alta resolução    |Não    |Sim (requer Exchange 2013 ou posterior)    |Sim    |
|Status de presença nos campos Microsoft Outlook From, To e Cc    |Sim    |Sim    |Sim    |
|Responder com IM ou chamada no menu disponibilidade    |Sim (a partir do cartão de visitas)    |Sim (a partir do cartão de visitas)    |Sim (a partir do cartão de visitas)    |
|Status de presença em uma solicitação de reunião na guia Assistente de Agendamento    |Sim    |Sim    |Não    |
|Responder com IM ou chamada da barra de ferramentas ou faixa de opções em uma mensagem de email recebida    |Sim    |Sim    |Sim    |
|**Outros Office aplicativos**   ||||
|OneNote anotações compartilhadas    |Não    |Sim    |Não    |
|Instalação integrada ao programa de Office de instalação    |Não    |Sim    |Não    |
|PowerPoint de apresentação    |Sim    |Sim (VBSS também disponível)    |Sim    |
|IM e presença em arquivos do Microsoft Word e Microsoft Excel (marcas inteligentes habilitadas)    |Somente Microsoft Word    |Somente Microsoft Word    |Não    |
|IM e presença em sites do Microsoft SharePoint (o Outlook deve estar instalado)    |Sim    |Sim    |Não    |
   
&#x2776; - Supõe que você instalou e está executando um Skype for Business no cliente Mac ou no cliente Lync 2011 para Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e Skype for Business

A tabela a seguir descreve Skype for Business suporte para várias versões do Exchange Server. O Outlook deve estar instalado no computador cliente para tratar chamadas MAPI estendidas e alguns recursos exigem o uso dos Serviços Web do Exchange (EWS).
  
**Skype for Business e Exchange Server Compatibilidade**

|**Exchange Server versão**|**Skype for Business suporte**|
|:-----|:-----|
|Exchange Server 2019 (somente Skype for Business Server 2019) |Igual ao Exchange Server 2013    |
|Exchange Server 2016    |Igual ao Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |O mesmo Exchange Server suporte a 2010, com a adição de  <br/>&bull;&nbsp;&nbsp;Unified Contact Store  <br/>&bull;&nbsp;&nbsp;Imagens de alta resolução  <br/>&bull;&nbsp;&nbsp;Integração de arquivamento  <br/> **Observação:** Para obter detalhes, [consulte Integrar Skype for Business Server com Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype for Business Server somente 2015) |Os recursos a seguir estão disponíveis somente através do EWS:  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens na pasta Histórico de Conversas  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens de caixa postal  <br/>&bull;&nbsp;&nbsp;Exibir informações de livre/ocupado estendidas e assunto e local da reunião  <br/>&bull;&nbsp;&nbsp;Exchange de contato  <br/> As pastas públicas são opcionais Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Confira também
 
[Windows de cliente e suporte a software](windows-requirements.md)
  
[Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)](meetings-clients.md)

