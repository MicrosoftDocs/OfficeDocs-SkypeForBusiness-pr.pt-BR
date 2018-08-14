---
title: Skype para compatibilidade de negócios com aplicativos do Office
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Entenda as maneiras que você pode acessar o Skype para recursos de negócios do Outlook e outros aplicativos do Microsoft Office.
ms.openlocfilehash: 22319a814ac1f09e67143f71a705c44b1e820e0e
ms.sourcegitcommit: 47f80b977fa7de3b83a521164f765623bffcf5c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2018
ms.locfileid: "22391837"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype para compatibilidade de negócios com aplicativos do Office
 
Entenda as maneiras que você pode acessar o Skype para recursos de negócios do Outlook e outros aplicativos do Microsoft Office.
  
Este tópico descreve a compatibilidade do Skype for Business com várias versões dos pacotes do Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype para negócios

A tabela a seguir descreve o Skype para recursos corporativos que são compatíveis com várias versões do Office quando o Exchange estiver implantado e integrado conforme descrito em [Integrar Skype para Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype para compatibilidade do Microsoft Office e de negócios**

|**Recurso**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|**2016 do Office para Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Recursos do Outlook** ||||
|Personalizar convites para reunião do Outlook (adicionar logotipo, URL de ajuda, aviso de isenção de responsabilidade, texto do rodapé)  |Não  |Sim   |Sim|
|Configurar a opção de reunião para ativar o mudo do áudio e vídeo do participante por padrão    |Não    |Sim    |Não    |
|Repositório unificado de contatos para gerenciar listas de contatos entre o Office e Skype para negócios    |Não    |Sim (requer o Exchange 2013 ou posterior)    |Sim    |
|Imagens de perfil de alta resolução    |Não    |Sim (requer o Exchange 2013 ou posterior)    |Sim    |
|Status de presença no Microsoft Outlook remetente, para, Cc campos e    |Sim    |Sim    |Sim    |
|Responder com IM ou chamada no menu de disponibilidade    |Sim (do cartão de visita)    |Sim (do cartão de visita)    |Sim (do cartão de visita)    |
|Status de presença em uma solicitação de reunião na guia Assistente de Agendamento    |Sim    |Sim    |Não    |
|Responder com IM ou chamada da barra de ferramentas ou faixa de opções em uma mensagem de email recebido    |Sim    |Sim    |Sim    |
|**Outros aplicativos do Office**   ||||
|Anotações compartilhadas do OneNote    |Não    |Sim    |Não    |
|Instalação integrada ao programa de instalação do Office    |Não    |Sim    |Não    |
|Conteúdo de apresentação do PowerPoint    |Sim    |Sim (VBSS também está disponível)    |Sim    |
|Mensagem instantânea e presença em arquivos do Microsoft Word e Microsoft Excel (marcas inteligentes habilitadas)    |Somente Microsoft Word    |Somente Microsoft Word    |Não    |
|Mensagem instantânea e presença em sites do Microsoft SharePoint (o Outlook deve estar instalado)    |Sim    |Sim    |Não    |
   
& #x 2776; -Pressupõe que você tenha instalado e que está sendo executadas um Skype for Business no cliente do Mac ou o Lync 2011 para o cliente do Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e do Skype para negócios

A tabela a seguir descreve Skype para suporte de negócios para diversas versões do Exchange Server. O Outlook deve estar instalado no computador cliente para administrar chamadas MAPI estendidas, e alguns recursos exigem o uso de EWS (Serviços Web do Exchange).
  
**Skype para comerciais e a compatibilidade do Exchange Server**

|**Versão do Exchange Server**|**Skype para suporte de negócios**|
|:-----|:-----|
|Exchange Server 2019 (Skype para Business Server 2019 somente) |Igual ao suporte para o Exchange Server 2013    |
|Exchange Server 2016    |Igual ao suporte para o Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Mesmo que o suporte do Exchange Server 2010, com a adição de  <br/>&bull;&nbsp;&nbsp;Repositório unificado de contatos  <br/>&bull;&nbsp;&nbsp;Imagens de alta resolução  <br/>&bull;&nbsp;&nbsp;Integração de arquivamento  <br/> **Observação:** Para obter detalhes, consulte [Integrar Skype para Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype para Business Server 2015 somente) |Os recursos a seguir estão disponíveis somente por meio do EWS:  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens na pasta Histórico da conversa  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens da caixa postal  <br/>&bull;&nbsp;&nbsp;Exibir informações de livre/ocupado estendidas e assunto da reunião e local  <br/>&bull;&nbsp;&nbsp;Sincronização de contatos do Exchange  <br/> Pastas públicas são opcionais no Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Consulte também
 
[Suporte de software e os requisitos de cliente do Windows](windows-requirements.md)
  
[Planejar para clientes de reuniões (Web App e reuniões App)](meetings-clients.md)

