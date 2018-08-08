---
title: Plano para o aplicativo de anúncio no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planejamento para o aplicativo de anúncio no Skype para Business Server Enterprise Voice, que configura o que fazer com que as chamadas telefônicas para números telefônicos não atribuídos em suas organizações. Inclui requisitos de arquivo de áudio.
ms.openlocfilehash: cfb39c986a423cb5a7c7fc6db51f649038014ec4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000504"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Plano para o aplicativo de anúncio no Skype para negócios 
 
Planejamento para o aplicativo de anúncio no Skype para Business Server Enterprise Voice, que configura o que fazer com que as chamadas telefônicas para números telefônicos não atribuídos em suas organizações. Inclui requisitos de arquivo de áudio.
  
O Skype para o aplicativo de anúncio de servidor de negócios permite que você configure o tratamento de chamadas telefônicas recebidas quando o número discado é válido para sua organização, mas não é atribuído a um usuário ou um telefone. É possível transferir essas ligações a um destino predeterminado (número de telefone, SIP URI ou correio de voz), ou reproduzir um anúncio de áudio, ou ainda ambos. O aplicativo de Anúncio ajuda a evitar situações em que o chamador disca para um número errado e ouve um tom de ocupado ou em que o cliente SIP recebe uma mensagem de erro. Esta seção inclui informações específicas para o aplicativo de anúncio de planejamento
  
Quando você implanta o aplicativo comunicado, você precisará configurar uma tabela de números não atribuídos que determina a ação a ser tomada quando alguém disca um número não atribuído. A tabela de números não atribuída contém intervalos de números de telefone são válidos para a organização e especifica qual aplicativo comunicado lida com cada intervalo. Quando um chamador disca o número de telefone que é válido para sua organização, mas não é atribuído a ninguém, Skype para Business Server pesquisará o número na tabela roteamento número não atribuído, identifica qual intervalo o número cai em e encaminha a chamada para o Aplicativo de anúncio especificado para aquele intervalo. O aplicativo de anúncio atende a chamada e reproduz uma mensagem de áudio (se você configurou para fazê-lo) e desconecta a chamada ou transfere para um destino predeterminado, tais como para um operador. Você pode usar o Skype para cmdlets do Shell de gerenciamento do servidor de negócios para configurar várias mensagens de áudio ou para destinos de transferência.
  
A forma como você configura a tabela de número não atribuído depende de como você deseja usá-la. Se você possui números específicos que não estão mais em uso e deseja reproduzir mensagens que são personalizadas para cada número, é possível inserir esses números específicos na tabela de número não atribuído. Por exemplo, se você alterou o número do seu atendimento ao cliente, é possível inserir o número do serviço antigo e associá-lo a um anúncio que oferece o novo número. Se você deseja reproduzir uma mensagem geral para qualquer pessoa que ligar para um número não atribuído, como funcionários que deixaram a organização, é possível inserir intervalos para todas as extensões válidas em sua organização. A tabela de número não atribuído é invocada sempre que um chamador liga para um número que não está atribuído atualmente.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

Aplicativo comunicado a é instalado automaticamente com o aplicativo grupo de resposta. Os aplicativos de anúncio e grupo de resposta são componentes padrão de uma implantação do Enterprise Voice: quando você implanta o Enterprise Voice, ambos os aplicativos serão implantados automaticamente. 
  
### <a name="software-requirements"></a>Requisitos de software 

Todos os servidores Front-End ou Standard Edition servidores que executam o aplicativo de anúncio devem ter o Windows Media Format Runtime instalado para servidores que executam o Windows Server 2008 R2 ou Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou Windows Server 2012 R2. Para Windows Server 2008 R2, o Windows Media Format Runtime é instalado como parte da experiência de área de trabalho do Windows. Windows Media Format Runtime ou Microsoft Foundation de mídia é necessário para arquivos do Windows Media Audio (. wma) que executa o aplicativo de comunicado para anúncios e música. 
  
### <a name="port-requirements"></a>Requisitos de porta

O aplicativo de anúncio usa a **porta 5071** para solicitações de escuta SIP.
    
> [!NOTE]
> Essa porta é a configuração padrão, que você pode alterar usando o cmdlet **Set-CsApplicationServer** . Para obter detalhes sobre esse cmdlet, consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de anúncio suporta o formato de arquivo Wave (. wav) e Windows Media audio (. wma) formato de arquivo para músicas e comunicados. Requisitos do arquivo de áudio para o aplicativo de anúncio são iguais do aplicativo grupo de resposta. Para obter detalhes, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).
  

