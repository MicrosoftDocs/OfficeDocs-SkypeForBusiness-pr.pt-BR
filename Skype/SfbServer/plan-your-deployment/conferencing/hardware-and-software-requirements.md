---
title: Requisitos de hardware e software para conferências no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Resumo: Leia este tópico para saber mais sobre os requisitos de hardware e software para conferências no Skype para Business Server.'
ms.openlocfilehash: 0029bca57477d52e1886ff476984477bdac75b97
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23247666"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisitos de hardware e software para conferências no Skype para Business Server

**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para conferências no Skype para Business Server.

Esta seção descreve os requisitos de hardware e software para webconferências, conferências de áudio e vídeo (A/V), conferência discada e conferência por IM (mensagens instantâneas). Todos os recursos de conferência são executados em Servidores Front-End; há requisitos adicionais para diferentes tipos de conferência, conforme mostrado no diagrama a seguir.

Por exemplo, se você quiser permitir que a conferência discada, você precisará implantar um servidor de mediação e um gateway para conexão com a rede telefônica pública comutada (PSTN). Se você deseja permitir Webconferência, você precisará garantir que Skype para Business Server pode se conectar a um servidor do Office Web Apps. Se você quiser permitir que usuários externos participem de conferências, será necessário implantar um Servidor de Borda.

**Funcionalidades e requisitos de conferência**

![Componentes de conferência](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Para obter mais informações sobre considerações de topologia, consulte [planejar sua topologia de conferência para Skype para Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisitos de hardware e software para Servidores Front-End

Porque Webconferência, A / V conferência, conferência discada e conferência de mensagens Instantâneas são colocados com o servidor Front-End, os requisitos de hardware e software do servidor são iguais aos servidores Front-End. Para obter detalhes sobre esses requisitos, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [requisitos de ambiente para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisitos de webconferência

Se você optou por habilitar a webconferência, será necessário planejar:

- O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.

- Integração com o Servidor do Office Web Apps, necessária para compartilhar arquivos do PowerPoint durante uma conferência.

### <a name="file-store"></a>Repositório de Arquivos

O Skype para serviço de webconferência Business Server armazena o conteúdo compartilhado durante as reuniões no armazenamento de arquivos. Como parte da implantação, você deve especificar um compartilhamento de arquivo a ser usado como o repositório de arquivos para o servidor Standard Edition ou pool de Front End do Enterprise Edition. Você pode usar um repositório de arquivos existente ou especificar um novo compartilhamento de arquivos determinando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos em que o repositório estará localizado e um nome de pasta para o novo compartilhamento de arquivos. Para obter mais informações, consulte [criar um compartilhamento de arquivo no Skype para Business Server](../../deploy/install/create-a-file-share.md). O serviço de webconferências criptografa o conteúdo antes de armazená-lo no repositório de arquivos.

Skype para Business Server suporta o uso de compartilhamentos de arquivos em armazenamento anexado diretamente (DAS) ou uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e em uma matriz redundante de discos independentes (RAID) para repositórios de arquivos. Depois que o Skype para o Assistente de implantação do Business Server definiu o local do compartilhamento de arquivo, Skype para Business Server cria uma estrutura de pastas em um compartilhamento de arquivo semelhante a:

- 1-ApplicationServer-1

- CentralMgmt-1-1

- WebServices-1-1

  - CollabContent

  - CollabMetadata

  - DataConf

O serviço de webconferências então armazena conteúdo como slides do PowerPoint, quadros de comunicações, votações e anexos nas pastas CollabContent e CollabMetadata, localizadas na pasta WebServices.

### <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para usar os recursos de webconferência, você deve instalar o Office Web Apps Server e configura o Skype para Business Server para se comunicar com o Office Web Apps Server.

Office Web Apps Server deve ser instalado em um computador autônomo que não está executando o Skype para Business Server, SQL Server ou qualquer outro aplicativo para servidores. (Você não deve ter qualquer versão do Office instalada no computador.) Qualquer computador usado para executar o Office Web Apps Server também deve ter um conjunto específico de software instalado (incluindo o .NET Framework 4.5 e Windows PowerShell 3.0). Esses requisitos, juntamente com informações sobre como configurar certificados e dos serviços de informações da Internet (IIS), são abordados em detalhes no [site de implantação do Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525).

Para obter informações sobre como configurar Skype para Business Server funcionar com o Office Web Apps Server, consulte [Configure integração com o Office Web Apps Server no Skype para Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisitos para conferência de áudio e vídeo

Para planejar a conferência A/V, você precisa saber a largura de banda de rede necessária para o tipo de mídia de conferência que sua organização requer. Isso pode incluir áudio, vídeo e vídeo panorâmico. Sem largura de banda suficiente, a experiência do usuário pode ser gravemente prejudicada.

Para obter informações sobre planejamento para conferências de capacidade de áudio e vídeo, consulte [planejar requisitos de rede de Skype para negócios](../../plan-your-deployment/network-requirements/network-requirements.md).

Você pode usar o controle de admissão de chamadas (CAC) para gerenciar a largura de banda de rede usada pelo / conferência V. Isso é importante para redes restritos, como links de largura de banda limitada entre central e sites de filiais. Para obter detalhes, consulte [Planejar o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Se você implantar uma conferência de áudio na sua rede, os usuários precisarão de dispositivos de áudio, como fones de ouvido, para participar de uma conferência. Se você implantar conferência de vídeo, precisará implantar dispositivos de vídeo, como webcams para usuários. Para os dispositivos de áudio e vídeo, a implantação e o treinamento do usuário são etapas importantes a considerar. Para obter mais informações, consulte [plano para clientes e dispositivos](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Para garantir uma experiência ideal ao usuário, a Microsoft recomenda que você use dispositivos de comunicações unificadas (UC) certificados pela Microsoft para todos os tipos de dispositivos. Para obter detalhes sobre os dispositivos de certificado para UC, consulte [telefones e dispositivos para Skype para negócios](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Requisitos para conferência discada

Conferência discada é um recurso opcional do Skype para carga de trabalho de conferência de Business Server que inclui uma variedade de componentes. Alguns dos componentes são específicas para conferência discada e alguns componentes do Enterprise Voice. Esta seção descreve os requisitos para os componentes necessários para conferência discada. Para obter detalhes sobre o servidor de mediação e requisitos de gateway telefônica pública comutada (PSTN) de rede, consulte o [componente de servidor de mediação em Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e [implantar um servidor de mediação no construtor de topologia no Skype para Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componentes necessários

Você precisará instalar o seguinte Skype para componentes de servidor de negócios antes de você pode configurar conferência discada:

- UCAS (Unified Communications Application Service) (chamado de  Serviço de Aplicativos)

- Aplicativo Atendedor de Conferência

- Aplicativo Comunicado de Conferência

- Página da Web Configurações de Conferência Discada

- Pelo menos um Servidor de Mediação e pelo menos um gateway PSTN

Para conferência discada, o serviço de aplicativo, o aplicativo Atendedor de conferência e o aplicativo de anúncio de conferência apresentam os mesmos requisitos de sistema operacional, como servidores Front-End. Para obter detalhes, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Aplicativo Atendedor de conferência e o aplicativo de anúncio de conferência requerem que o Windows Media Format Runtime é instalado nos servidores Front-End. O Windows Media Format é exigido para reproduzir arquivos WMA (Windows Media Audio) que são usados para músicas em espera, nomes gravados e prompts. Se você estiver instalando no Windows Server 2012 ou Windows Server 2012 R2 (que é recomendável), você precisará instalar o Microsoft Foundation de mídia para obter o Windows Media Format Runtime. Se você estiver instalando em qualquer versão do Windows Server antes do Windows 2012, precisará certificar-se de que o Windows Desktop Experience está instalado para obter o Windows Media Format Runtime.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de arquivo de áudio para conferência discada

Skype para Business Server não oferece suporte a personalização de prompts de voz e música para conferência discada. No entanto, se você tiver uma necessidade de negócios forte que requer que você altere os arquivos de áudio padrão, consulte o artigo da Base de Conhecimento Microsoft 961177, [como personalizar os prompts de voz ou arquivos de música para serviços de audioconferência discada](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

Você também pode usar o utilitário de gerenciamento [Microsoft Lync Server Conferencing Attendant personalizado Prompts de voz](https://go.microsoft.com/fwlink/p/?LinkId=396880) , que permite que os administradores substituir os prompts de voz padrão usados quando um chamador telefone ingressa em uma Skype para reunião de negócios com os prompts personalizados para fornecer uma reunião diferente experiência de entrada. Os prompts de voz personalizados podem ser instalados em um servidor Enterprise ou Standard Edition.

Aplicativo Atendedor de conferência e o aplicativo de anúncio de conferência têm os seguintes requisitos para música de espera, nome gravado e arquivos de prompt de áudio:

- Formato de arquivo WMA (áudio do Windows Media)

- 16 bits mono

- 48 kbps 2-pass CBR (taxa de bits constante)

- Nível da fala a -24 DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos do usuário para conferência discada

Os usuários de conferências discadas devem ter um número de telefone ou extensão exclusivos atribuídos à respectiva conta. Este requisito oferece suporte à autenticação durante a conferência discada. Usuários empresariais (ou seja, usuários que têm credenciais do Active Directory Domain Services e Skype para contas Business Server dentro da sua organização) Insira seu número de telefone (ou extensão) e um número de identificação pessoal (PIN) para discar para conferências como um usuário autenticado.

## <a name="port-requirements-for-conferencing"></a>Requisitos de porta para conferência

Para usar os recursos de conferência, Skype para Business Server requer que determinadas portas estão abertas. A tabela a seguir lista requisitos de porta para conferência. Para obter detalhes sobre todos os requisitos de porta, consulte [requisitos de porta e protocolo para servidores](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Portas do servidor necessárias**


|**Função de servidor**|**Nome do serviço**|**Porta**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Skype para o serviço de conferência de mensagens Instantâneas do servidor de negócios  <br/> |5062  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de Webconferência de servidor de negócios  <br/> |8057  <br/> |TCP (TLS)  <br/> |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de compatibilidade de webconferência Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Usado para escutar conexões do modelo de objeto Persistent Shared (PSOM) do cliente do Live Meeting e de versões anteriores do Skype para Business Server.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de conferência de áudio/vídeo do Business Server  <br/> |5063  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de conferência de áudio/vídeo do Business Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para videoconferência.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço Atendedor de conferência Business Server (conferência discada)  <br/> |5064  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência discada.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço Atendedor de conferência Business Server (conferência discada)  <br/> |5072  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para Atendedor (discada).  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de anúncio de conferência do servidor de negócios  <br/> |5073  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para o Skype para serviço de anúncio de conferência do servidor de negócios (ou seja, para conferência discada).  <br/> |
|Todos os servidores internos  <br/> |Vários  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usada para audioconferência em todos os servidores internos. Usado por todos os servidores que encerram áudio: servidores Front-End (para Skype para o serviço Atendedor de conferência do servidor de negócios, Skype para serviço de anúncio de conferência do servidor de negócios e Skype para o serviço de conferência de áudio/vídeo do Business Server), e Servidor de mediação.  <br/> |
|Servidor Office Web Apps  <br/> ||443  <br/> ||Usada pelo Skype para Business Server para se conectar ao servidor do Office Web Apps.  <br/> |

**Portas necessárias do cliente**


|**Porta**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Usada para acesso de usuário externo às sessões de webconferência.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de porta de vídeo (mínimo de 20 portas necessárias).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Compartilhamento de aplicativos.  <br/> |


