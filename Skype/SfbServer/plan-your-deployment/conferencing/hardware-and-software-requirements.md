---
title: Requisitos de hardware e software para conferência em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Resumo: leia este tópico para saber mais sobre os requisitos de hardware e software para conferência em Skype for Business Server.'
ms.openlocfilehash: 4cb6192475b56d78d1cf03b69eea86b67c05519f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859888"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisitos de hardware e software para conferência em Skype for Business Server

**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para conferência em Skype for Business Server.

Esta seção descreve os requisitos de hardware e software para conferência da Web, conferência de áudio e vídeo (A/V), conferência discda e conferência de mensagens instantâneas (IM). Todos os recursos de conferência são executados em Servidores Front-End; há requisitos adicionais para diferentes tipos de conferência, conforme mostrado no diagrama a seguir.

Por exemplo, se você quiser permitir conferência discda, precisará implantar um Servidor de Mediação e um gateway para se conectar à PSTN (rede telefônica pública comutado). Se quiser permitir a webconferência, você precisará garantir que Skype for Business Server possa se conectar a um servidor Office Web Apps. Se você quiser permitir que usuários externos participem de conferências, será necessário implantar um Servidor de Borda.

**Requisitos e recursos de conferência**

![Componentes de conferência.](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Para obter mais informações sobre considerações de topologia, consulte [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisitos de hardware e software para servidores front-end

Como a webconferência, conferência A/V, conferência discada e conferência de IM são todos alocados com o Servidor Front-End, os requisitos de hardware e software do servidor são os mesmos dos Servidores Front-End. Para obter detalhes sobre esses requisitos, consulte Requisitos de servidor [para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e requisitos ambientais para [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou requisitos de [servidor para Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisitos para webconferência

Se você optou por habilitar a webconferência, será necessário planejar:

- O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.

- Integração com Office Web Apps Server, o que é necessário para compartilhar PowerPoint arquivos durante uma conferência.

### <a name="file-store"></a>Repositório de Arquivos

O Skype for Business Server de webconferência armazena conteúdo compartilhado durante reuniões no armazenamento de arquivos. Como parte da implantação, você deve especificar um compartilhamento de arquivos a ser usado como o armazenamento de arquivos para o servidor Edição Standard ou Edição Enterprise pool de front-end. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos. Para obter mais informações, [consulte Create a file share in Skype for Business Server](../../deploy/install/create-a-file-share.md). O serviço de webconferências criptografa o conteúdo antes de armazená-lo no repositório de arquivos.

Skype for Business Server suporte ao uso de compartilhamentos de arquivos no DAS (armazenamento conectado direto) ou em uma san (rede de área de armazenamento), incluindo DFS (Sistema de Arquivos Distribuídos) e em uma matriz redundante de discos independentes (RAID) para armazenamentos de arquivos. Depois que Skype for Business Server Assistente de Implantação tiver definido o local do compartilhamento de arquivos, Skype for Business Server criar uma estrutura de pasta no compartilhamento de arquivos semelhante a:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

O serviço de webconferências então armazena conteúdo como slides do PowerPoint, quadros de comunicações, votações e anexos nas pastas CollabContent e CollabMetadata, localizadas na pasta WebServices.

### <a name="office-web-apps-server"></a>Servidor do Office Web Apps

Para usar recursos de webconferência, você deve instalar Office Web Apps Server e configurar o Skype for Business Server para se comunicar com o Office Web Apps Server.

Office O Servidor web apps deve ser instalado em um computador autônomo que não está executando Skype for Business Server, SQL Server ou qualquer outro aplicativo de servidor. (Você não deve ter nenhuma versão Office instalada nesse computador.) Qualquer computador usado para executar Office Web Apps Server também deve ter um conjunto específico de software instalado (incluindo .NET Framework 4.5 e Windows PowerShell 3.0). Esses requisitos, juntamente com informações sobre a configuração de certificados e Serviços de Informações da Internet (IIS), são discutidos em detalhes no site de Implantação Microsoft Office [Web Apps.](/webappsserver/deploy-the-infrastructure-office-web-apps-server)

Para obter informações sobre como configurar Skype for Business Server para trabalhar com Office Web Apps Server, consulte [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisitos para conferência de áudio e vídeo

Para planejar a conferência A/V, você precisa saber a largura de banda de rede necessária para o tipo de mídia de conferência que sua organização requer. Isso pode incluir áudio, vídeo e vídeo panorâmico. Sem largura de banda de rede suficiente, a experiência do usuário pode ser gravemente degradada.

Para obter informações sobre o planejamento de capacidade de áudio e vídeo para conferências, consulte [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

Você pode usar o CAC (controle de admissão de chamada) para gerenciar a largura de banda de rede usada pela conferência A/V. Isso é importante para redes restritas, como links de largura de banda limitados entre sites centrais e filiais. Para obter detalhes, [consulte Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Se você implantar uma conferência de áudio na sua rede, os usuários precisarão de dispositivos de áudio, como fones de ouvido, para participar em uma conferência de áudio. Se você implantar conferência de vídeo, será necessário implantar dispositivos de vídeo, como webcams, para os usuários. Para dispositivos de áudio e vídeo, a implantação de dispositivos e o treinamento do usuário são etapas importantes a serem consideradas. Para obter mais informações, consulte [Plan for clients and devices](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). A Microsoft recomenda que você use dispositivos de comunicações unificadas (UC) certificados pela Microsoft para todos os tipos de dispositivos, para garantir uma experiência de usuário ideal. Para obter detalhes sobre dispositivos certificados por UC, consulte [Telefones e dispositivos para Skype for Business](../../../SfbPartnerCertification/certification/devices-ip-phones.md).

## <a name="requirements-for-dial-in-conferencing"></a>Requisitos para conferência discagem

A conferência discagem é um recurso opcional da carga de trabalho Skype for Business Server conferência que inclui uma variedade de componentes. Alguns destes componentes são específicos para conferência discada e alguns são componentes do Enterprise Voice. Esta seção descreve os requisitos para os componentes necessários para conferência discagem. Para obter detalhes sobre os requisitos de gateway PSTN (Servidor de Mediação e rede telefônica pública comutado), consulte Componente do Servidor de Mediação no [Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e Implantar um Servidor de Mediação no Construtor de [Topologias Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componentes necessários

Você precisará instalar os seguintes componentes Skype for Business Server antes de configurar a conferência discagem:

- UCAS (Unified Communications Application Service) (chamado de Serviço de Aplicativo)

- Aplicativo Atendedor de Conferência

- Aplicativo Comunicado de Conferência

- Página da Web Configurações de Conferência Discada

- Pelo menos um Servidor de Mediação e pelo menos um gateway PSTN

Para conferência discda, o serviço de aplicativo, aplicativo Atendedor de Conferência e aplicativo Comunicado de Conferência têm os mesmos requisitos do sistema operacional que os Servidores Front-End. Para obter detalhes, consulte [Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

aplicativo Atendedor de Conferência e aplicativo Comunicado de Conferência exigem que Windows Tempo de Execução de Formato de Mídia seja instalado em Servidores Front-End. Windows O Tempo de Execução de Formato de Mídia é necessário para reproduzir Windows arquivos de áudio de mídia (WMA) usados para música em espera, nomes gravados e prompts. Se você estiver instalando no Windows Server 2012 ou Windows Server 2012 R2 (o que recomendamos), será necessário instalar o Microsoft Media Foundation para obter Windows Tempo de Execução de Formato de Mídia. Se você estiver instalando em qualquer versão do Windows Server antes do Windows 2012, você precisará garantir que Windows Experiência de Área de Trabalho do Windows seja instalada para obter Windows Tempo de Execução de Formato de Mídia.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de arquivo de áudio para conferência discda

Skype for Business Server não dá suporte à personalização de prompts de voz e música para conferência discada. No entanto, se você tiver uma necessidade comercial forte que exija que você altere os arquivos de áudio padrão, consulte o artigo da Base de Dados de Conhecimento da Microsoft 961177, Como personalizar prompts de voz ou arquivos de música para conferência de áudio [discado](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

aplicativo Atendedor de Conferência e aplicativo Comunicado de Conferência os seguintes requisitos para arquivos de música em espera, nome gravado e prompt de áudio:

- Formato de arquivo WMA (áudio do Windows Media)

- 16 bits mono

- 48 kbps 2-pass CBR (taxa de bits constante)

- Nível da fala a -24 DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos do usuário para conferência discda

Os usuários de conferências discadas devem ter um número de telefone ou extensão exclusivos atribuídos à respectiva conta. Este requisito oferece suporte à autenticação durante a conferência discada. Enterprise usuários (ou seja, usuários que possuem credenciais de Serviços de Domínio do Active Directory e contas Skype for Business Server em sua organização) insiram o número de telefone (ou extensão) e um PIN (número de identificação pessoal) para discar para conferências como um usuário autenticado.

## <a name="port-requirements-for-conferencing"></a>Requisitos de porta para conferência

Para usar os recursos de conferência, o Skype for Business Server exige que determinadas portas sejam abertas. A tabela a seguir lista os requisitos de porta para conferência. Para obter detalhes sobre todos os requisitos de porta, consulte [Port and protocol requirements for servers](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Portas de servidor necessárias**


|**Função de servidor**|**Nome do serviço**|**Port**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Skype for Business Server Serviço de Conferência de IM  <br/> |5062  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Serviço de WebConferência  <br/> |8057  <br/> |TCP (TLS)  <br/> |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Serviço de Compatibilidade de WebConferência  <br/> |8058  <br/> |TCP (TLS)  <br/> |Usado para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente Live Meeting e versões anteriores Skype for Business Server.  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Serviço de Audioconferência de Vídeo  <br/> |5063  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Serviço de Audioconferência de Vídeo  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para videoconferência.  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Atendedor de Conferência serviço (conferência discda)  <br/> |5064  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência discada.  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Atendedor de Conferência serviço (conferência discda)  <br/> |5072  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para o Attendant (discagem em conferência).  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Serviço de Compartilhamento de Aplicativos  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Serviço de Compartilhamento de Aplicativos  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server Comunicado de Conferência serviço  <br/> |5073  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada Skype for Business Server Comunicado de Conferência serviço de Skype for Business Server Comunicado de Conferência (ou seja, para conferência discagem).  <br/> |
|Todos os servidores internos  <br/> |Vários  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para audioconferência em todos os servidores internos. Usado por todos os servidores que encerram o áudio: Servidores front-end (para serviço Skype for Business Server Atendedor de Conferência, Skype for Business Server Comunicado de Conferência serviço e Skype for Business Server Serviço de Conferência de Áudio/Vídeo) e Servidor de Mediação.  <br/> |
|Office Servidores Web Apps  <br/> ||443  <br/> ||Usado por Skype for Business Server para se conectar ao Office Web Apps.  <br/> |

**Portas de cliente necessárias**


|**Port**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Usada para acesso de usuário externo às sessões de webconferência.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Usado para acesso de usuário externo a sessões E/V e mídia (UDP)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervalo de porta de vídeo (mínimo de 20 portas necessárias)  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Compartilhamento de aplicativos  <br/> |