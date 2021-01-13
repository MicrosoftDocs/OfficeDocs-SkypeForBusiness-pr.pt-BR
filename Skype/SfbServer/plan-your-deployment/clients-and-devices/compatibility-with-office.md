---
title: Compatibilidade do Skype for Business com aplicativos do Office
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Entenda as maneiras como você pode acessar os recursos do Skype for Business no Outlook e em outros aplicativos do Microsoft Office.
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802731"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilidade do Skype for Business com aplicativos do Office
 
Entenda as maneiras como você pode acessar os recursos do Skype for Business no Outlook e em outros aplicativos do Microsoft Office.
  
Este tópico descreve a compatibilidade do Skype for Business com várias versões dos pacote do Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype for Business

A tabela a seguir descreve os recursos do Skype for Business que são suportados por várias versões do Office depois que o Exchange é implantado e integrado conforme descrito em Integrar o Skype for Business Server com [o Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
**Compatibilidade do Skype for Business e do Microsoft Office**

|**Característica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|**Office 2016 para Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Recursos do Outlook** ||||
|Personalizar convites de reunião do Outlook (adicionar logotipo, URL de ajuda, aviso de isenção de responsabilidade, texto do rodapé)  |Não  |Sim   |Sim|
|Configurar a opção de reunião para desativar o áudio e o vídeo do participante por padrão    |Não    |Sim    |Não    |
|Unified Contact Store for managing Contacts lists across Office and Skype for Business    |Não    |Sim (requer o Exchange 2013 ou posterior)    |Sim    |
|Imagens de perfil de alta resolução    |Não    |Sim (requer o Exchange 2013 ou posterior)    |Sim    |
|Status de presença nos campos De, Para e Cc do Microsoft Outlook    |Sim    |Sim    |Sim    |
|Responder com IM ou chamada no menu de disponibilidade    |Sim (a partir do cartão de visitas)    |Sim (a partir do cartão de visitas)    |Sim (a partir do cartão de visitas)    |
|Status de presença em uma solicitação de reunião na guia Assistente de Agendamento    |Sim    |Sim    |Não    |
|Responder com IM ou chamada da barra de ferramentas ou da faixa de opções em uma mensagem de email recebida    |Sim    |Sim    |Sim    |
|**Outros aplicativos do Office**   ||||
|Anotações compartilhadas do OneNote    |Não    |Sim    |Não    |
|Instalação integrada ao programa de instalação do Office    |Não    |Sim    |Não    |
|Conteúdo de apresentação do PowerPoint    |Sim    |Sim (VBSS também disponível)    |Sim    |
|IM e presença em arquivos do Microsoft Word e Microsoft Excel (marcas inteligentes habilitadas)    |Somente Microsoft Word    |Somente Microsoft Word    |Não    |
|IM e presença em sites do Microsoft SharePoint (o Outlook deve estar instalado)    |Sim    |Sim    |Não    |
   
&#x2776; - Presume que você tenha instalado e atualmente está executando um cliente do Skype for Business no Mac ou o cliente do Lync 2011 para Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e Skype for Business

A tabela a seguir descreve o suporte do Skype for Business para várias versões do Exchange Server. O Outlook deve estar instalado no computador cliente para tratar chamadas MAPI estendidas e alguns recursos exigem o uso dos Serviços Web do Exchange (EWS).
  
**Compatibilidade do Skype for Business e do Exchange Server**

|**Versão do Exchange Server**|**Suporte do Skype for Business**|
|:-----|:-----|
|Exchange Server 2019 (apenas Skype for Business Server 2019) |Mesmo que o suporte do Exchange Server 2013    |
|Exchange Server 2016    |Mesmo que o suporte do Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Mesmo que o suporte do Exchange Server 2010, com a adição de  <br/>&bull;&nbsp;&nbsp;Armazenamento unificado de contatos  <br/>&bull;&nbsp;&nbsp;Imagens em alta resolução  <br/>&bull;&nbsp;&nbsp;Integração de arquivamento  <br/> **Observação:** Para obter detalhes, consulte [Integrar o Skype for Business Server ao Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Exchange Server 2010  <br/>(Skype for Business Server 2015 somente) |Os recursos a seguir estão disponíveis somente através do EWS:  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens na pasta Histórico da Conversa  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens de caixa postal  <br/>&bull;&nbsp;&nbsp;Exibir informações de livre/ocupado estendidas e assunto e local da reunião  <br/>&bull;&nbsp;&nbsp;Sincronização de contatos do Exchange  <br/> As pastas públicas são opcionais no Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Confira também
 
[Requisitos de cliente do Windows e suporte a software](windows-requirements.md)
  
[Planejar-se para clientes de reuniões (aplicativo Web App e Reuniões)](meetings-clients.md)

