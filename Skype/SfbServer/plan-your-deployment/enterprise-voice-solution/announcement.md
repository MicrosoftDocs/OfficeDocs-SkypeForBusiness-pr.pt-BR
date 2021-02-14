---
title: Planejar o aplicativo Comunicado no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Planejamento do aplicativo de comunicados no Skype for Business Server Enterprise Voice, que configura o que fazer com chamadas telefônicas para números de telefone não atribuídos em suas organizações. Inclui requisitos de arquivo de áudio.
ms.openlocfilehash: b1929fa14b105fd8eccd0f178ae7ef77c1bdf086
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813751"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planejar o aplicativo Comunicado no Skype for Business

Planejamento do aplicativo de comunicados no Skype for Business Server Enterprise Voice, que configura o que fazer com chamadas telefônicas para números de telefone não atribuídos em suas organizações. Inclui requisitos de arquivo de áudio.

O aplicativo Comunicado do Skype for Business Server permite configurar o tratamento de chamadas telefônicas recebidas quando o número discado é válido para sua organização, mas não é atribuído a um usuário ou telefone. Você pode transferir essas chamadas para um destino predeterminado (número de telefone, URI do SIP ou caixa postal), reproduzir um comunicado de áudio ou ambos. O aplicativo Comunicado ajuda você a evitar situações em que um chamador faz uma indialidade e ouve um tom de ocupado ou o cliente SIP recebe uma mensagem de erro. Esta seção inclui informações de planejamento específicas para o aplicativo Comunicado

Ao implantar o aplicativo Comunicado, você precisa configurar uma tabela de números não atribuídos que determina a ação a ser tomada quando alguém discar um número não atribuído. A tabela de números não atribuídos contém intervalos de números de telefone que são válidos para a organização e especifica qual aplicativo de Anúncio lida com cada intervalo. Quando um chamador disca um número de telefone válido para sua organização, mas não é atribuído a ninguém, o Skype for Business Server procura o número na tabela de roteamento de números não atribuídos, identifica em qual intervalo o número se enquadra e encaminha a chamada para o aplicativo comunicado especificado para esse intervalo. O aplicativo Comunicado atende a chamada e reproduz uma mensagem de áudio (se você configurá-la para fazer isso) e, em seguida, desconecta a chamada ou a transfere para um destino predeterminado, como para um operador. Você pode usar os cmdlets do Shell de Gerenciamento do Skype for Business Server para configurar várias mensagens de áudio ou transferir destinos.

Como você configura a tabela de número não atribuído depende de como você deseja usá-la. Se você possui números específicos que não estão mais em uso e deseja reproduzir mensagens que são personalizadas para cada número, é possível inserir estes números específicos na tabela de número não atribuído. Por exemplo, se você alterou o número do seu atendimento ao cliente, é possível inserir o número do serviço antigo e associá-lo com um anúncio que oferece o novo número. Se você deseja reproduzir uma mensagem geral para qualquer pessoa que ligar para um número não atribuído, como funcionários que deixaram a organização, é possível inserir intervalos para todas as extensões válidas em sua organização. A tabela de número não atribuído é invocada sempre que um ligador chama um número que não está atribuído atualmente.

## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo Comunicado é instalado automaticamente com o aplicativo Grupo de Resposta. Os aplicativos Comunicado e Grupo de Resposta são componentes padrão de uma implantação do Enterprise Voice: quando você implanta o Enterprise Voice, ambos os aplicativos são implantados automaticamente.

### <a name="software-requirements"></a>Requisitos de software

Todos os servidores Front End ou Standard Edition que executam o aplicativo Comunicado devem ter o Windows Media Format Runtime instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o Tempo de Execução do Windows Media Format é instalado como parte da Experiência Desktop do Windows. O Windows Media Format Runtime ou o Microsoft Media Foundation são necessários para arquivos .wma (Windows Media Audio) que o aplicativo Comunicado reproduz para comunicados e música.

### <a name="port-requirements"></a>Requisitos de porta

O aplicativo Comunicado usa **a Porta 5071 para** solicitações de escuta SIP.

> [!NOTE]
> Essa porta é a definição padrão, que você pode modificar usando o cmdlet **Set-CsApplicationServer**. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de Gerenciamento do Skype for Business Server.

### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo Comunicado dá suporte ao formato de arquivo Wave (.wav) e ao formato de arquivo de áudio Windows Media (.wma) para música e comunicados. Os requisitos de arquivo de áudio para o aplicativo Comunicado são os mesmos do aplicativo Grupo de Resposta. Para detalhes, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


