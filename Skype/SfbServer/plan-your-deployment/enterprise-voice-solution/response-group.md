---
title: Planejar o aplicativo Grupo de Resposta no Skype for Business Server
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
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planejamento de grupos de resposta no Skype for Business Server Enterprise Voice, que permite configurar o roteamento de chamadas para grupos de usuários. Inclui requisitos de arquivo de áudio.
ms.openlocfilehash: 5abf043531079e8eef707b8cdfc4efe70f8be4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813471"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Planejar o aplicativo Grupo de Resposta no Skype for Business Server

Planejamento de grupos de resposta no Skype for Business Server Enterprise Voice, que permite configurar o roteamento de chamadas para grupos de usuários. Inclui requisitos de arquivo de áudio.

Se sua organização tiver grupos de pessoas que respondem e gerenciam determinados tipos de chamadas, como para atendimento ao cliente, suporte técnico interno ou suporte por telefone geral para um departamento, você pode implantar o aplicativo Grupo de Resposta para gerenciar esses tipos de chamadas. O aplicativo Grupo de Resposta encaminha e enfilros chamadas de entrada para pessoas designadas, que são conhecidas como agentes. Você pode aumentar o uso de serviços de suporte telefônico e reduzir a sobrecarga de execução desses serviços usando grupos de resposta.

Quando um chamador chama um grupo de resposta, a chamada é roteada para um agente com base em um grupo de busca ou mas respostas do chamador para as perguntas de IVR (resposta de voz interativa). O aplicativo Grupo de Resposta usa métodos de roteamento de grupo de resposta padrão para rotear a chamada para o próximo agente disponível. Os métodos de roteamento de chamada suportados incluem serial, ocioso por mais tempo, paralelo, round robin e roteamento do Attendant (ou seja, todos os agentes são chamados ao mesmo tempo para cada chamada de entrada, independentemente de sua presença atual).

Se não houverem agentes disponíveis, a chamada será mantida em uma fila até que um agente esteja disponível. Enquanto está na fila, o chamador ouve música até um agente disponível aceitar a chamada. Se a fila estiver cheia ou se a chamada se desconectar enquanto estiver na fila, o chamador poderá ouvir uma mensagem e, em seguida, será desconectado ou transferido para um destino diferente, como um número de telefone ou caixa postal diferente. Quando um agente aceita a chamada, o chamador pode ou não ser capaz de ver a identidade do agente, dependendo de como o administrador configura o grupo de resposta. Os agentes podem ser formais, o que significa que eles devem entrar no grupo antes de aceitar chamadas encaminhadas para o grupo, ou informais, que significa que eles não precisam entrar no grupo para aceitar chamadas.

> [!NOTE]
> Apenas os usuários locais podem ser operadores. Se um operador for movido de local para online, a chamada do grupo de resposta não será mais roteada para ele.

> [!NOTE]
> O aplicativo Grupo de Resposta usa um serviço interno, chamado Match Making, para enfilerar chamadas e encontrar agentes disponíveis. Cada computador que executa o aplicativo Grupo de Resposta executa o serviço Match Making, mas apenas um serviço Match Making por pool está ativo por vez, os outros são passivos. Se o serviço Correspondência ativo ficar indisponível durante uma paralisação não planejada, um dos serviços Correspondência passivos ficará ativo. O aplicativo Grupo de Resposta faz o melhor para garantir que o roteamento e a fila de chamadas continue sem interrupções. No entanto, quando ocorre uma transição do serviço Correspondência, todas as chamadas em transferência no momento são perdidas. Por exemplo, se a transição for devido à queda do Servidor front-end, todas as chamadas que estão sendo manipuladas pelo serviço Match Making ativo nesse Servidor front-end também serão perdidas.

## <a name="response-group-workflows"></a>Fluxos de trabalho do grupo de resposta

Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada. O fluxo de trabalho especifica a fila que deve ser usada para colocar a chamada em espera, o método de roteamento a ser usado para grupos de busca e as perguntas e respostas a serem usadas com grupos de resposta interativa. Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.

> [!NOTE]
> É necessário criar grupos de agentes e filas antes de criar um fluxo de trabalho que os use.

## <a name="management-of-response-groups"></a>Gerenciamento de grupos de resposta

No Skype for Business Server, duas funções de gerenciamento estão disponíveis para gerenciamento de grupos de resposta: Gerente do Grupo de Resposta e Administrador do Grupo de Resposta. Os Administradores do Grupo de Resposta podem gerenciar qualquer aspecto de qualquer grupo de resposta. Gerentes do Grupo de Resposta podem gerenciar apenas determinados aspectos e apenas para os grupos de resposta de sua propriedade. A função Gerente pode ajudá-lo a reduzir os custos de administração, pois você pode delegar responsabilidades limitadas para grupos de resposta específicos a qualquer usuário habilitado para o Enterprise Voice. Observe que um usuário pode ser um Gerente do Grupo de Resposta e um Administrador do Grupo de Resposta.

Para acomodar a função Gerente, o aplicativo Grupo de Resposta usa **um** Tipo de Fluxo de Trabalho Gerenciado ou Não Gerenciado. A tabela a seguir descreve os grupos de respostas Gerenciado ou Não gerenciado.

**Grupos de respostas Gerenciado ou Não gerenciado**

|**Tipo de grupo de respostas**|**Descrição**|
|:-----|:-----|
|Não-managed  <br/> | Os grupos de respostas não gerenciados não têm gerentes atribuídos. Somente o Administrador do Grupo de Resposta pode configurar esses grupos de resposta. <br/>  Vários grupos de respostas não gerenciados podem compartilhar uma fila ou grupo de agentes. <br/>  Quando você migra grupos de resposta de uma versão anterior para o Skype for Business Server, o tipo é definido como Não-Managed. <br/> |
|Gerenciado  <br/> | Os Administradores do Grupo de Resposta podem configurar qualquer aspecto dos grupos de resposta gerenciados. <br/>  Gerentes do Grupo de Resposta não podem exibir ou modificar grupos de resposta que não estão explicitamente atribuídos a eles. <br/>  Gerentes do Grupo de Resposta podem definir apenas algumas configurações para os grupos de resposta que são explicitamente atribuídos a eles. <br/>  Os grupos de respostas gerenciados não podem compartilhas filas nem grupos de agentes com outros grupos de respostas, sejam gerenciados ou não gerenciados. <br/> |

A tabela a seguir descreve as ações que os Gerentes do Grupo de Resposta podem e não podem executar para os grupos de resposta atribuídos a eles.

**Recursos do gerente do grupo de respostas**

|**Pode configurar:**|**Pode criar, excluir ou configurar:**|**Não é possível:**|
|:-----|:-----|:-----|
| Agentes <br/>  Mensagem de boas-vindas <br/>  Nome do Grupo de Resposta <br/>  Descrição <br/>  Número de exibição <br/>  Horário comercial <br/>  Música de espera <br/>  Status (ativo/inativo) <br/>  Fluxos de trabalho de grupo de busca ou fluxos de trabalho de IVR (reposta interativa de voz) <br/> | Grupos de agentes <br/>  Filas <br/>  Conjuntos de feriados <br/> | Criar ou excluir qualquer tipo de fluxo de trabalho <br/>  Modificar configurações centrais do grupo de respostas, como: **URI do SIP**, **Número de Telefone** ou **Tipo de Fluxo de Trabalho**.  <br/> |

Gerentes do Grupo de Resposta podem usar as ferramentas a seguir para gerenciar seus grupos de resposta designados.

- Painel de Controle do Skype for Business Server

    > [!NOTE]
    > Gerentes do Grupo de Resposta só podem gerenciar as configurações do Grupo de Resposta com essa ferramenta. Outras configurações do Skype for Business Server não estão disponíveis para Gerentes.

- Ferramenta de Configuração do Grupo de Resposta

- Shell de Gerenciamento do Skype for Business Server

O Grupo de Resposta é bem dimensionado para ambientes de departamento ou grupo de trabalho (para obter detalhes, consulte [Capacity Planning for Response Group)](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)e pode ser implantado em instalações de telefonia inteiramente novas. Ele dá suporte a chamadas de entrada da implantação do Enterprise Voice e da rede da operadora local. Os agentes podem usar o Skype for Business, o Lync 2013, o Lync 2010, o Lync 2010 Attendant ou o Lync Phone Edition para atender às chamadas roteados para eles.

## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo Grupo de Resposta é habilitado automaticamente quando você implanta o Enterprise Voice.

### <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

O aplicativo Grupo de Resposta tem os mesmos requisitos de hardware, requisitos do sistema operacional e pré-requisitos de software que os Servidores Front-End.

Se você usar arquivos Windows Media Audio (.wma) para música e comunicados do Grupo de Resposta, todos os Servidores Front End ou servidores Standard Editions que executam o aplicativo Grupo de Resposta deverão ter o Tempo de Execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o Windows Media Format Runtime é instalado como parte da Experiência Desktop do Windows.

O Grupo de Resposta **usa pacotes de idiomas para** dar suporte a texto em fala e reconhecimento de fala. Essas tecnologias de fala são usadas ao configurar mensagens, como a mensagem de boas-vindas e outros prompts, e questões e respostas de IVR (resposta interativa de voz). Por padrão, os 26 pacotes de idiomas com suporte são instalados quando você implanta o Skype for Business Server.

### <a name="port-requirements"></a>Requisitos de porta

O aplicativo Grupo de Resposta usa as seguintes portas:

- **Porta 5071 para**   solicitações de escuta SIP

- **Porta 8404 para**   comunicações entre servidores

    > [!NOTE]
    > Essa porta é usada para o serviço De corresponder e é necessária quando o aplicativo grupo de resposta é implantado em um pool que tem mais de um servidor front-end.

   > [!NOTE]
   > Essas portas são as configurações padrão que podem ser alteradas com o uso do cmdlet **Set-CsApplicationServer**. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de Gerenciamento do Skype for Business Server.

### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo Grupo de Resposta oferece suporte ao formato de arquivo wave (.wav) e ao formato de arquivo de áudio Windows Media (.wma) para mensagens do Grupo de Resposta, música de espera ou perguntas ivr (resposta interativa de voz).

O formato de arquivo de áudio do Windows Media requer que o Tempo de Execução do Windows Media Format seja instalado em Servidores Front End que executam o Windows Server 2008 R2 e o Windows Server 2008. Para mais detalhes, consulte "Requisitos de software", anteriormente nesta seção.

#### <a name="supported-wave-file-formats"></a>Formatos de arquivo wave suportados

Todos os arquivos wave devem atender aos seguintes requisitos:

- Arquivo de 8 ou 16 bits

- Formato de modulação de código de pulso linear (LPCM), A-Law ou mu-Law

- Mono ou estéreo

- 4 MB ou menos

Para o melhor desempenho de arquivos wave, um  arquivo Wave mono, de 16 kHz e 16 bits é recomendado.

#### <a name="supported-windows-media-audio-file-formats"></a>Formatos de arquivo de áudio Windows Media

Se você utilizar um arquivo de áudio Windows Media, considere utilizar taxas de bit baixos e verifique o desempenho do sistema sob carga.

Você pode utilizar o Microsoft Expression Encoder 4 para converter um arquivo para o formato Windows Media Audio. Para baixar o Expression Encoder 4, consulte [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) .

### <a name="response-group-configuration-tool-requirements"></a>Requisitos de ferramenta de configuração de Grupo de resposta

A Ferramenta de Configuração do Grupo de Resposta oferece suporte às combinações de sistemas operacionais e navegadores da Web descritas na tabela a seguir.

> [!NOTE]
> Há suporte para as versões de 32 bits e 64 bits dos sistemas operacionais. Somente versões de 32 bits do Internet Explorer são compatíveis.

**Sistemas operacionais e navegadores da Web suportados**

|**Sistema operacional**|**Navegador da Web**|
|:-----|:-----|
|Windows Vista com Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 com Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Console de agente do Grupo de resposta

O console de agente suporta as combinações de sistemas operacionais e navegadores da web descritas na tabela a seguir.

> [!NOTE]
> Versões 32 bits ou 64 bits do sistema operacional são suportadas. Apenas versões 32 bits do Internet Explorer são suportadas.

**Sistemas operacionais e navegadores da Web suportados**

|**Sistema operacional**|**Navegador da Web**|
|:-----|:-----|
|Windows Vista com Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 com Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Suporte ao cliente

O aplicativo Grupo de Resposta oferece suporte aos seguintes clientes:

- Cliente de área de trabalho do Skype for Business

- Cliente de área de trabalho do Lync 2013

- Cliente de área de trabalho do Lync 2010

- Lync 2010 Attendant

- Atendedor do Office Communications Server 2007 R2

- Lync Phone Edition

> [!NOTE]
> O aplicativo Grupo de Resposta não é suportado em clientes móveis do Lync.

O cliente específico que você pode usar depende do tipo de usuário do Grupo de Resposta que você é:

- **Chamadores** podem chamar um grupo de resposta usando quaisquer clientes listados anteriormente e usando um telefone padrão através da rede telefônica pública comutada (PSTN).

- **Agentes informais** (agentes que não fazem login e saída de seus grupos para aceitar chamadas) podem aceitar chamadas usando Attendant, Lync ou Lync Phone Edition. Os agentes informais são automaticamente assinados em seus grupos ao entrar no Skype for Business Server usando um desses clientes.

- Agentes **formais** (agentes que devem entrar e sair de seus grupos para aceitar chamadas) podem aceitar chamadas usando o Skype for Business e acessando o console do agente no item de menu ou usando o Attendant e acessando o console do agente diretamente do Internet Explorer.

## <a name="capacity-planning"></a>Planejamento de capacidade

A tabela a seguir descreve o modelo de usuário do Grupo de Resposta que você pode usar como base para requisitos de planejamento de capacidade.

> [!NOTE]
> Os números na tabela a seguir assumem que arquivos de 16 kHz, mono, Wave (.wav) de 16 bits sejam usados para todos os arquivos de áudio do grupo de resposta. Se você usa outros formatos de arquivo, como Windows Media Audio (.wma), os números podem variar.

> [!IMPORTANT]
> Tenha em mente que para planejar a capacidade de recuperação de desastres, cada pool de um pool pareado deve poder lidar com cargas de trabalho de todos os grupos de resposta, em ambos os pools.

**Modelo de Usuário do Grupo de Resposta**

|**Indicador**|**Por pool enterprise edition  <br/> (com 8 servidores front-end)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Chamadas de entrada por segundo  <br/> |16   <br/> |2   <br/> |
|Chamadas concorrentes conectadas ao IVR ou MoH  <br/> |480  <br/> |60  <br/> |
|Sessões anônimas concorrentes (sem IM)  <br/> |224  <br/> |28  <br/> |
|Sessões anônimas concorrentes (com IM)  <br/> |64  <br/> |8   <br/> |
|Operadores ativos (formais e informais)  <br/> |2400  <br/> |2400  <br/> |
|Número de grupos de busca  <br/> |800  <br/> |800  <br/> |
|Número de grupos IVR (usa reconhecimento de fala)  <br/> |400  <br/> |400  <br/> |


