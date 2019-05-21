---
title: Requisitos de hardware e software para conferências no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Resumo: Leia este tópico para saber mais sobre os requisitos de hardware e software para conferências no Skype for Business Server.'
ms.openlocfilehash: c4efb85c7ae1674cab7ee123833df779a835e14c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277339"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisitos de hardware e software para conferências no Skype for Business Server

**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para conferências no Skype for Business Server.

Esta seção descreve os requisitos de hardware e software para webconferências, conferências de áudio e vídeo (A/V), conferência discada e conferência por IM (mensagens instantâneas). Todos os recursos de conferência são executados em Servidores Front-End; há requisitos adicionais para diferentes tipos de conferência, conforme mostrado no diagrama a seguir.

Por exemplo, se você quiser permitir a conferência discada, será necessário implantar um servidor de mediação e um gateway para se conectar à rede telefônica pública comutada (PSTN). Se você quiser permitir a Webconferência, será necessário garantir que o Skype for Business Server possa se conectar a um servidor do Office Web Apps. Se você quiser permitir que usuários externos participem de conferências, será necessário implantar um Servidor de Borda.

**Funcionalidades e requisitos de conferência**

![Componentes de conferência](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Para obter mais informações sobre as considerações de topologia, consulte [planejar a topologia de conferência para o Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisitos de hardware e software para Servidores Front-End

Como a Webconferência, conferência A/V, conferência discada e conferência de mensagens instantâneas estão todas posicionadas com o servidor front-end, os requisitos de hardware e software do servidor são os mesmos para os servidores front-end. Para obter detalhes sobre esses requisitos, consulte [requisitos do servidor para o Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [requisitos ambientais para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos do servidor para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisitos de webconferência

Se você optou por habilitar a webconferência, será necessário planejar:

- O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.

- Integração com o Servidor do Office Web Apps, necessária para compartilhar arquivos do PowerPoint durante uma conferência.

### <a name="file-store"></a>Repositório de Arquivos

O serviço de conferência da Web do Skype for Business Server armazena conteúdo compartilhado durante reuniões no repositório de arquivos. Como parte da implantação, você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool Front-end da edição Enterprise. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos. Para obter mais informações, consulte [criar um compartilhamento de arquivos no Skype for Business Server](../../deploy/install/create-a-file-share.md). O serviço de webconferências criptografa o conteúdo antes de armazená-lo no repositório de arquivos.

O Skype for Business Server oferece suporte ao uso de compartilhamentos de arquivos em DAS (armazenamento de conexão direta) ou de uma SAN, incluindo o sistema de arquivos distribuído (DFS) e um conjunto redundante de discos independentes (RAID) para armazenamentos de arquivos. Depois que o assistente de implantação do Skype for Business Server tiver definido o local do compartilhamento de arquivos, o Skype for Business Server criará uma estrutura de pastas dentro do compartilhamento de arquivos semelhante a:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

O serviço de webconferências então armazena conteúdo como slides do PowerPoint, quadros de comunicações, votações e anexos nas pastas CollabContent e CollabMetadata, localizadas na pasta WebServices.

### <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para usar os recursos de webconferência, você deve instalar o Office Web Apps Server e configurar o Skype for Business Server para se comunicar com o servidor do Office Web Apps.

O Office Web Apps Server deve ser instalado em um computador autônomo que não esteja executando o Skype for Business Server, SQL Server ou qualquer outro aplicativo de servidor. (Você não deve ter qualquer versão do Office instalada nesse computador.) Qualquer computador usado para executar o Office Web Apps Server também deve ter um conjunto específico de softwares instalado (incluindo .NET Framework 4,5 e Windows PowerShell 3,0). Esses requisitos, juntamente com informações sobre a configuração de certificados e serviços de informações da Internet (IIS), são discutidos em detalhes no [site de implantação do Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525).

Para obter informações sobre como configurar o Skype for Business Server para trabalhar com o servidor do Office Web Apps, consulte [Configurar a integração com o servidor do Office Web Apps no Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisitos para conferência de áudio e vídeo

Para planejar a conferência A/V, você precisa saber a largura de banda de rede necessária para o tipo de mídia de conferência que sua organização requer. Isso pode incluir áudio, vídeo e vídeo panorâmico. Sem largura de banda suficiente, a experiência do usuário pode ser gravemente prejudicada.

Para obter informações sobre planejamento de funcionalidades de áudio e vídeo para conferências, consulte [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

Você pode usar o controle de admissão de chamadas (CAC) para gerenciar a largura de banda de rede usada por uma conferência A/V. Isso é importante para redes restritas, como links limitados de largura de banda entre sites centrais e filiais. Para obter detalhes, consulte [planejar o controle de admissão de chamadas no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Se você implantar uma conferência de áudio na sua rede, os usuários precisarão de dispositivos de áudio, como fones de ouvido, para participar de uma conferência. Se você implantar conferência de vídeo, precisará implantar dispositivos de vídeo, como webcams para usuários. Para os dispositivos de áudio e vídeo, a implantação e o treinamento do usuário são etapas importantes a considerar. Para obter mais informações, consulte [plano para clientes e dispositivos](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Para garantir uma experiência ideal ao usuário, a Microsoft recomenda que você use dispositivos de comunicações unificadas (UC) certificados pela Microsoft para todos os tipos de dispositivos. Para obter detalhes sobre dispositivos certificados pela UC, consulte [telefones e dispositivos do Skype for Business](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Requisitos para conferência discada

A conferência discada é um recurso opcional da carga de trabalho de conferência do Skype for Business Server que inclui diversos componentes. Alguns dos componentes são específicos para conferência discada e alguns são componentes do Enterprise Voice. Esta seção descreve os requisitos para os componentes necessários para a conferência discada. Para obter detalhes sobre os requisitos do gateway do servidor de mediação e da rede telefônica pública comutada (PSTN), consulte [componente do servidor de mediação no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e [implantação de um servidor de mediação no construtor de topologias no Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componentes necessários

Você precisará instalar os seguintes componentes do servidor do Skype for Business antes de poder configurar a conferência discada:

- UCAS (Unified Communications Application Service) (chamado de  Serviço de Aplicativos)

- Aplicativo Atendedor de Conferência

- Aplicativo Comunicado de Conferência

- Página da Web Configurações de Conferência Discada

- Pelo menos um Servidor de Mediação e pelo menos um gateway PSTN

Para conferência discada, serviço de aplicativo, aplicativo atendedor de conferência e aplicativo de anúncio de conferência têm os mesmos requisitos de sistema operacional que os servidores front-end. Para obter mais detalhes, consulte [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Aplicativo de atendedor de conferência o aplicativo de anúncio de conferência requer que o tempo de execução do Windows Media Format seja instalado em servidores front-end. O Windows Media Format é exigido para reproduzir arquivos WMA (Windows Media Audio) que são usados para músicas em espera, nomes gravados e prompts. Se estiver instalando no Windows Server 2012 ou no Windows Server 2012 R2 (que recomendamos), você precisará instalar o Microsoft Media Foundation para obter o tempo de execução do Windows Media Format. Se você estiver instalando em qualquer versão do Windows Server antes do Windows 2012, precisará certificar-se de que o Windows Desktop Experience está instalado para obter o Windows Media Format Runtime.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de arquivo de áudio para conferência discada

O Skype for Business Server não é compatível com a personalização de prompts de voz e música para conferência discada. No entanto, se você tiver uma forte necessidade empresarial que exija a alteração dos arquivos de áudio padrão, consulte o artigo 961177 da base de dados de conhecimento Microsoft, [como personalizar prompts de voz ou arquivos de música para conferências de áudio](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)discadas.

Você também pode usar o utilitário de gerenciamento de [solicitações de voz personalizado do Microsoft Lync Server Attendant](https://go.microsoft.com/fwlink/p/?LinkId=396880) , que permite aos administradores substituir as solicitações de voz padrão usadas quando um chamador de telefone ingressar em uma reunião do Skype for Business com avisos personalizados para fornecer uma experiência de entrada de reunião diferente. Os prompts de voz personalizados podem ser instalados em um servidor Enterprise ou Standard Edition.

Aplicativo de atendedor de conferência o aplicativo de anúncio de conferência tem os seguintes requisitos para músicas em espera, nomes gravados e arquivos de prompt de áudio:

- Formato de arquivo WMA (áudio do Windows Media)

- 16 bits mono

- 48 kbps 2-pass CBR (taxa de bits constante)

- Nível da fala a -24 DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos do usuário para conferência discada

Os usuários de conferências discadas devem ter um número de telefone ou extensão exclusivos atribuídos à respectiva conta. Este requisito oferece suporte à autenticação durante a conferência discada. Usuários corporativos (ou seja, os usuários que têm credenciais de serviços de domínio Active Directory e contas do Skype for Business Server dentro de sua organização) inserem o número de telefone (ou ramal) e um número de identificação pessoal (PIN) para discar para conferências como um usuário autenticado.

## <a name="port-requirements-for-conferencing"></a>Requisitos de porta para conferência

Para poder usar os recursos de conferência, o Skype for Business Server exige que determinadas portas estejam abertas. A tabela a seguir lista requisitos de porta para conferência. Para obter detalhes sobre todos os requisitos de portabilidade, consulte [requisitos de protocolo e porta para servidores](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Portas de servidor necessárias**


|**Função de servidor**|**Nome do serviço**|**Porta**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Serviço de conferência de mensagens instantâneas do Skype for Business Server  <br/> |5062  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  <br/> |
|Servidores Front-End  <br/> |Serviço do Skype for Business Server Web de Webconferência  <br/> |8057  <br/> |TCP (TLS)  <br/> |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  <br/> |
|Servidores Front-End  <br/> |Serviço de compatibilidade de conferência da Web do Skype for Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Usado para ouvir conexões do modelo de objeto compartilhado persistente (PSOM) do cliente de reunião ao vivo e versões anteriores do Skype for Business Server.  <br/> |
|Servidores Front-End  <br/> |Serviço de conferência de áudio/vídeo do Skype for Business Server  <br/> |5063  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  <br/> |
|Servidores Front-End  <br/> |Serviço de conferência de áudio/vídeo do Skype for Business Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para videoconferência.  <br/> |
|Servidores Front-End  <br/> |Serviço de atendedor de conferência do Skype for Business Server (conferência discada)  <br/> |5064  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência discada.  <br/> |
|Servidores Front-End  <br/> |Serviço de atendedor de conferência do Skype for Business Server (conferência discada)  <br/> |5072  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada do atendente (discagem por conferência).  <br/> |
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
|Servidores Front-End  <br/> |Serviço de anúncio de conferências do Skype for Business Server  <br/> |5073  <br/> |TCP  <br/> |Usado para solicitações SIP recebidas para o serviço de anúncio de conferência do Skype for Business Server (ou seja, para conferência discada).  <br/> |
|Todos os servidores internos  <br/> |Vários  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usada para audioconferência em todos os servidores internos. Usado por todos os servidores que terminam o áudio: servidores front-end (para serviço de atendedor de conferência do Skype for Business Server, serviço de anúncio de conferência do Skype for Business Server e serviço de conferência de áudio/vídeo do Skype for Business Server) e Servidor de mediação.  <br/> |
|Servidor Office Web Apps  <br/> ||443  <br/> ||Usado pelo Skype for Business Server para se conectar ao servidor do Office Web Apps.  <br/> |

**Portas de cliente necessárias**


|**Porta**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Usada para acesso de usuário externo às sessões de webconferência.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de porta de vídeo (mínimo de 20 portas necessárias).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Compartilhamento de aplicativos.  <br/> |


