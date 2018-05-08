---
title: Skype para compatibilidade de negócios com aplicativos do Office
ms.author: jambirk
author: jambirk
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
ms.openlocfilehash: 186b8951718e6903ec7cc4f8c317504b74917716
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype para compatibilidade de negócios com aplicativos do Office
 
Entenda as maneiras que você pode acessar o Skype para recursos de negócios do Outlook e outros aplicativos do Microsoft Office.
  
Este tópico descreve a compatibilidade do Skype for Business com várias versões dos pacotes do Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype para negócios

A tabela a seguir descreve o Skype para recursos corporativos que são compatíveis com várias versões do Office quando o Exchange estiver implantado e integrado conforme descrito em [Integrar Skype para 2015 do servidor de negócios com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype para compatibilidade do Microsoft Office e de negócios**

|**Recurso**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|**2016 do Office para Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Recursos do Outlook** <br/> ||||
|Personalizar convites para reunião do Outlook (adicionar logotipo, URL de ajuda, aviso de isenção de responsabilidade, texto do rodapé)  <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|Configurar a opção de reunião para ativar o mudo do áudio e vídeo do participante por padrão  <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|Repositório unificado de contatos para gerenciar listas de contatos entre o Office e Skype para negócios  <br/> |Não  <br/> |Sim (requer o Exchange 2013 ou posterior)  <br/> |Sim  <br/> |
|Imagens de perfil de alta resolução  <br/> |Não  <br/> |Sim (requer o Exchange 2013 ou posterior)  <br/> |Sim  <br/> |
|Status de presença no Microsoft Outlook remetente, para, Cc campos e  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Responder com IM ou chamada no menu de disponibilidade  <br/> |Sim (do cartão de visita)  <br/> |Sim (do cartão de visita)  <br/> |Sim (do cartão de visita)  <br/> |
|Status de presença em uma solicitação de reunião na guia Assistente de Agendamento  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Responder com IM ou chamada da barra de ferramentas ou faixa de opções em uma mensagem de email recebido  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|**Outros aplicativos do Office** <br/> ||||
|Anotações compartilhadas do OneNote  <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|Instalação integrada ao programa de instalação do Office  <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|Conteúdo de apresentação do PowerPoint  <br/> |Sim  <br/> |Sim  <br/> (VBSS também disponível)  <br/> |Sim  <br/> |
|Mensagem instantânea e presença em arquivos do Microsoft Word e Microsoft Excel (marcas inteligentes habilitadas)  <br/> |Somente Microsoft Word  <br/> |Somente Microsoft Word  <br/> |Não  <br/> |
|Mensagem instantânea e presença em sites do Microsoft SharePoint (o Outlook deve estar instalado)  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
   
& #x 2776; -Pressupõe que você tenha instalado e que está sendo executadas um Skype for Business no cliente do Mac ou o Lync 2011 para o cliente do Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e do Skype para negócios

A tabela a seguir descreve Skype para suporte de negócios para diversas versões do Exchange Server. O Outlook deve estar instalado no computador cliente para administrar chamadas MAPI estendidas, e alguns recursos exigem o uso de EWS (Serviços Web do Exchange).
  
**Skype para comerciais e a compatibilidade do Exchange Server**

|**Versão do Exchange Server**|**Skype para suporte de negócios**|
|:-----|:-----|
|Exchange Server 2016  <br/> |Igual ao suporte para o Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Mesmo que o suporte do Exchange Server 2010, com a adição de  <br/>&bull;&nbsp;&nbsp;Repositório unificado de contatos  <br/>&bull;&nbsp;&nbsp;Imagens de alta resolução  <br/>&bull;&nbsp;&nbsp;Integração de arquivamento  <br/> **Observação:** Para obter detalhes, consulte [Integrar Skype para 2015 do servidor de negócios com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/> |Os recursos a seguir estão disponíveis somente por meio do EWS:  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens na pasta Histórico da conversa  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens da caixa postal  <br/>&bull;&nbsp;&nbsp;Exibir informações de livre/ocupado estendidas e assunto da reunião e local  <br/>&bull;&nbsp;&nbsp;Sincronização de contatos do Exchange  <br/> Pastas públicas são opcionais no Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Consulte também
 

[Suporte de software e os requisitos de cliente do Windows](windows-requirements.md)
  
[Planejar para clientes de reuniões (Web App e reuniões App)](meetings-clients.md)
#### 

[Interoperabilidade do cliente no Lync 2013](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[Requisitos de sistema do cliente](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Requisitos de aplicativo da Windows Store do Lync](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)

