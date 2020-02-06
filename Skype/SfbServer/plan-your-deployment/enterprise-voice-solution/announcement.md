---
title: Planejar o aplicativo de anúncio no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planejamento do aplicativo de anúncio no Skype for Business Server Enterprise Voice, que configura o que fazer com chamadas telefônicas para números de telefone não atribuídos em suas organizações. Inclui requisitos de arquivo de áudio.
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803261"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planejar o aplicativo de anúncio no Skype for Business

Planejamento do aplicativo de anúncio no Skype for Business Server Enterprise Voice, que configura o que fazer com chamadas telefônicas para números de telefone não atribuídos em suas organizações. Inclui requisitos de arquivo de áudio.

O aplicativo de anúncio do Skype for Business Server permite que você configure o tratamento de chamadas telefônicas de entrada quando o número discado é válido para sua organização, mas não é atribuído a um usuário ou a um telefone. É possível transferir essas ligações a um destino predeterminado (número de telefone, SIP URI ou correio de voz), ou reproduzir um anúncio de áudio, ou ainda ambos. O aplicativo de Anúncio ajuda a evitar situações em que o chamador disca para um número errado e ouve um tom de ocupado ou em que o cliente SIP recebe uma mensagem de erro. Esta seção inclui informações de planejamento específicas do aplicativo de lançamento

Ao implantar o aplicativo de anúncio, você precisa configurar uma tabela de número não atribuído que determine a ação a ser tomada quando alguém discar um número não atribuído. A tabela número não atribuído contém intervalos de números de telefone que são válidos para a organização e especifica qual aplicativo de anúncio manipula cada intervalo. Quando um chamador disca para um número de telefone válido para a sua organização, mas não está atribuído a ninguém, o Skype for Business Server procura o número na tabela de roteamento de números não atribuídos, identifica o intervalo no qual o número cai e roteia a chamada para o Aplicativo de anúncio especificado para esse intervalo. O aplicativo de anúncio atende a chamada e reproduz uma mensagem de áudio (se você a configurou para fazer isso) e, em seguida, desconectará a chamada ou a transferirá para um destino predeterminado, por exemplo, para um operador. Você pode usar cmdlets do Shell de gerenciamento do Skype for Business Server para configurar várias mensagens de áudio ou para transferir destinos.

A forma como você configura a tabela de número não atribuído depende de como você deseja usá-la. Se você possui números específicos que não estão mais em uso e deseja reproduzir mensagens que são personalizadas para cada número, é possível inserir esses números específicos na tabela de número não atribuído. Por exemplo, se você alterou o número do seu atendimento ao cliente, é possível inserir o número do serviço antigo e associá-lo a um anúncio que oferece o novo número. Se você deseja reproduzir uma mensagem geral para qualquer pessoa que ligar para um número não atribuído, como funcionários que deixaram a organização, é possível inserir intervalos para todas as extensões válidas em sua organização. A tabela de número não atribuído é invocada sempre que um chamador liga para um número que não está atribuído atualmente.

## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo de anúncio o é instalado automaticamente com o aplicativo de grupo de resposta. Os aplicativos de anúncio e de grupo de resposta são componentes padrão de uma implantação do Enterprise Voice: ao implantar o Enterprise Voice, esses dois aplicativos são implantados automaticamente.

### <a name="software-requirements"></a>Requisitos de software

Todos os servidores de front-end ou servidores Standard Edition que executam o aplicativo de anúncio devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. O tempo de execução do Windows Media Format ou do Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que o aplicativo de anúncio reproduz para anúncios e música.

### <a name="port-requirements"></a>Requisitos de porta

O aplicativo de anúncio usa a **porta 5071** para solicitações de escuta SIP.

> [!NOTE]
> Essa porta é a definição padrão, que você pode modificar usando o cmdlet  **Set-CsApplicationServer**. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Skype for Business Server.

### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de anúncio aceita o formato de arquivo Wave (. wav) e o formato de áudio do Windows Media (. WMA) para músicas e anúncios. Os requisitos de arquivo de áudio para o aplicativo de anúncio são iguais aos do aplicativo de grupo de resposta. Para detalhes, consulte  [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


