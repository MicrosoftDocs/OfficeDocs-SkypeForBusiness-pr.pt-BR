---
title: Compatibilidade do Skype for Business com aplicativos do Office
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Compreenda como você pode acessar os recursos do Skype for Business a partir do Outlook e de outros aplicativos do Microsoft Office.
ms.openlocfilehash: c24c6b08e21db357d52b1cc130e53f23b6123ff6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277430"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilidade do Skype for Business com aplicativos do Office
 
Compreenda como você pode acessar os recursos do Skype for Business a partir do Outlook e de outros aplicativos do Microsoft Office.
  
Este tópico descreve a compatibilidade do Skype for Business com várias versões dos pacotes do Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype for Business

A tabela a seguir descreve os recursos do Skype for Business com suporte em várias versões do Office quando o Exchange é implantado e integrado, conforme descrito em [integrar o Skype for Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Compatibilidade entre o Skype for Business e o Microsoft Office**

|**Recurso**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|&#x2776; **do Office 2016 para Mac** |
|:-----|:-----|:-----|:-----|
|**Recursos do Outlook** ||||
|Personalizar convites para reunião do Outlook (adicionar logotipo, URL de ajuda, aviso de isenção de responsabilidade, texto do rodapé)  |Não  |Sim    |Sim |
|Configurar a opção de reunião para ativar o mudo do áudio e vídeo do participante por padrão    |Não    |Sim    |Não    |
|Repositório de contatos unificado para gerenciamento de listas de contatos no Office e no Skype for Business    |Não    |Sim (requer o Exchange 2013 ou posterior)    |Sim    |
|Imagens de perfil de alta resolução    |Não    |Sim (requer o Exchange 2013 ou posterior)    |Sim    |
|Status de presença nos campos de, para e CC do Microsoft Outlook    |Sim     |Sim     |Sim     |
|Responder com mensagem instantânea ou ligar no menu de disponibilidade    |Sim (do cartão de visita)    |Sim (do cartão de visita)    |Sim (do cartão de visita)    |
|Status de presença em uma solicitação de reunião na guia Assistente de Agendamento    |Sim     |Sim    |Não    |
|Responder com mensagem instantânea ou ligar da barra de ferramentas ou da faixa de opções em uma mensagem de email recebida    |Sim     |Sim     |Sim     |
|**Outros aplicativos do Office**   ||||
|Anotações compartilhadas do OneNote    |Não    |Sim    |Não    |
|Instalação integrada ao programa de instalação do Office    |Não    |Sim    |Não    |
|Conteúdo de apresentação do PowerPoint    |Sim    |Sim (VBSS também disponível)    |Sim    |
|Mensagem instantânea e presença em arquivos do Microsoft Word e Microsoft Excel (marcas inteligentes habilitadas)    |Somente Microsoft Word    |Somente Microsoft Word    |Não    |
|Mensagem instantânea e presença em sites do Microsoft SharePoint (o Outlook deve estar instalado)    |Sim    |Sim    |Não    |
   
&#x2776;-pressupõe que você instalou e está executando um cliente Skype for Business no Mac ou o Lync 2011 para Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e Skype for Business

A tabela a seguir descreve o suporte do Skype for Business para várias versões do Exchange Server. O Outlook deve estar instalado no computador cliente para administrar chamadas MAPI estendidas, e alguns recursos exigem o uso de EWS (Serviços Web do Exchange).
  
**Compatibilidade entre o Skype for Business e o Exchange Server**

|**Versão do Exchange Server**|**Suporte do Skype for Business**|
|:-----|:-----|
|Exchange Server 2019 (somente o Skype for Business Server 2019) |Igual ao suporte para o Exchange Server 2013    |
|Exchange Server 2016    |Igual ao suporte para o Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Mesmo que o suporte do Exchange Server 2010, com a adição de  <br/>&bull;&nbsp;&nbsp;Repositório de contatos unificado  <br/>&bull;&nbsp;&nbsp;Imagens de alta resolução  <br/>&bull;&nbsp;&nbsp;Integração de arquivamento  <br/> **Observação:** Para obter detalhes, consulte [integrar o Skype for Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Somente Skype for Business Server 2015) |Os recursos a seguir estão disponíveis somente por meio do EWS:  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens na pasta histórico da conversa  <br/>&bull;&nbsp;&nbsp;Ler ou excluir itens da caixa postal  <br/>&bull;&nbsp;&nbsp;Exibir informações de disponibilidade estendidas e assunto e local da reunião  <br/>&bull;&nbsp;&nbsp;Sincronização de contatos do Exchange  <br/> Pastas públicas são opcionais no Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Confira também
 
[Requisitos do cliente Windows e suporte de software](windows-requirements.md)
  
[Plano para clientes de reuniões (aplicativo Web e aplicativo reuniões)](meetings-clients.md)

