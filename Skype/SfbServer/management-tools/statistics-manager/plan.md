---
title: Planejar para o Gerenciador de estatísticas de Skype Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumo: Leia este tópico para saber mais sobre o Gerenciador de estatísticas para Skype para Business Server.'
ms.openlocfilehash: a7cd9fd3dd3eff7f1c9b0326d45475f95f9a909c
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2018
ms.locfileid: "26283198"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planejar para o Gerenciador de estatísticas de Skype Business Server

**Resumo:** Leia este tópico para saber mais sobre o Gerenciador de estatísticas para Skype para Business Server.

 Gerenciador de estatísticas para Skype para Business Server é uma ferramenta poderosa que permite que você visualize Skype para dados de integridade e desempenho do servidor de negócios em tempo real. Você pode sondar dados de desempenho em centenas de servidores por cada alguns segundos e exiba os resultados instantaneamente no site do Gerenciador de estatísticas.

Você pode usar o Gerenciador de estatísticas para identificar problemas de desempenho em andamento, exiba os resultados de uma alteração planejada ao seu ambiente, para controlar a resolução de interrupções e muito mais. Imediato, gerente de estatísticas é configurado com limites de indicador de integridade de chave (KHI) e pode ser personalizado para atender às necessidades exclusivas da sua implantação.

Você pode implantar o Gerenciador de estatísticas em uma implantação no local em que um único servidor hospeda todos os componentes do Gerenciador de estatísticas do servidor. Para obter mais informações sobre como implantar o Gerenciador de estatísticas, consulte [Implantar o Gerenciador de estatísticas para Skype para Business Server](deploy.md). Se você já tiver uma implantação existente do Gerenciador de estatísticas, mas você ainda não tiver atualizado para a versão 2.0, consulte [o que há de novo na versão 2.0](plan.md#BKMK_WhatsNew) e [Atualizar o Gerenciador de estatísticas para Skype para Business Server](upgrade.md).

Este tópico inclui as seguintes seções:

- [Recursos e capacidades](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)

- [O que há de novo na versão 2.0](plan.md#BKMK_WhatsNew)

- [Componentes](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)

- [Implantação no local](plan.md#BKMK_DeploymentOptions)

- [Requisitos](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)

- [Considerações de segurança](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Recursos e capacidades
<a name="BKMK_Features"> </a>

Gerenciador de estatísticas permite que você:

- Exibir dados brutos para todos os servidores em tempo real. (Dados em uma muito alta taxa de amostra e enviados para o site em menos de um segundo.)

- Exibir os dados que são agregados para uma função específica; Por exemplo, servidor Front-End, servidor de mediação, servidor de borda e assim por diante.

- Ver os detalhes de dados de modo de exibição de sites específicos, pools específicos dentro do site e os servidores, em seguida, específicos dentro do pool.

- Crie gráficos personalizados para escolhido contadores são mostrados por padrão.

- Aplicar zoom e panorâmica em ambos o x e y-eixos ou no eixo x apenas.

- Use os intervalos de data ou pontos em tempo para filtrar dados.

- Exibir o desempenho do servidor com base em indicadores de integridade de chave estabelecida (KHIs). KHIs representam um conjunto de contadores de desempenho com um intervalo definido de Íntegro.

- Exiba métricas detalhadas de cada contador.

- Compare dados entre vários servidores ou população.

- Exibir relatórios de contador latente para identificar os operadores que não são relatórios dados atuais para o serviço de painel.

- Salve uma instância específica de dados do gráfico em um arquivo.

- Modo de exibição KHIs em tempo real, incluindo atualizações. Se o modo de exibição de histórico estiver habilitado, apenas novas falhas são mostradas.

  - Exibir todos os KHIs ao mesmo tempo

  - Exibir KHIs pelo servidor (modo paisagem)

  - Exibir KHI definições

## <a name="whats-new-in-release-20"></a>O que há de novo na versão 2.0
<a name="BKMK_WhatsNew"> </a>

O exemplo a seguir descreve o que há de novo na versão 2.0. Se você tiver uma implantação existente do Gerenciador de estatísticas e você ainda não tiver atualizado, consulte [Atualizar o Gerenciador de estatísticas para Skype para Business Server](upgrade.md).

- Modos de exibição do cenário foram adicionados para a mídia de borda, integridade malha, Failover de Pool e cenários de registro.

- Muitos novos contadores foram adicionados para SQL servers, mais Skype contadores de uso de negócios e assim por diante.

- Integração do nó de inspetor para o agente do Gerenciador de estatísticas - se o agente está instalado em um nó de Inspetor, ele reportará estatísticas de transação sintética como contadores ao Gerenciador de estatísticas.

- Diversos aperfeiçoamentos de desempenho e confiabilidade.

Para verificar a versão do site do Gerenciador de estatísticas você está executando:

- No Gerenciador de arquivos, abra (diretório padrão) C:\Program Files\Skype para Business Server StatsMan WebSite\bin

- Clique com o botão direito em StatsManHubWebSite.dll e exiba suas propriedades

- A versão do produto será mostrada nos detalhes de Descrição.

## <a name="components"></a>Componentes
<a name="BKMK_Components"> </a>

Gerenciador de estatísticas consiste dos seguintes componentes:

- **Agente.** Um agente leve executado em cada servidor monitorado. O agente permite sondagem configurável alta taxa de contadores de desempenho com a agregação de local.

- **Ouvinte.** A API de lado do servidor que recebe os dados de todos os operadores e agrega os dados população.

- **Hub.** Serve como a API do cliente para o sistema, é executado em todos os servidores web e fornece as atualizações de dados em tempo real para os clientes conectados por meio do site. (O Hub é instalado automaticamente como parte do msi do site).

- **Site da Web.** Uma interface de usuário que reúne todos os recursos disponíveis no sistema.

Além disso, o Gerenciador de estatísticas requer **relacionada**, um servidor de estrutura de dados de código aberto para armazenar em cache na memória. Para obter mais informações sobre como baixar relacionada, consulte [Implantar o Gerenciador de estatísticas](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Implantação no local
<a name="BKMK_DeploymentOptions"> </a>

Em uma implantação local, um único servidor hospeda todos os componentes do Gerenciador de estatísticas do servidor.

O diagrama a seguir mostra uma implantação local, no qual o site do Gerenciador de estatísticas, Hub, ouvinte e relacionada no sistema de armazenamento em cache são hospedados em uma única máquina. Gerenciador de estatísticas está monitorando três Skype para servidores de negócios, cada um deles têm um único operador transmitir dados para o ouvinte. Os usuários se conectar a um único site para exibir todos os dados agregados pelo Gerenciador de estatísticas:

![Implantação local do Gerente de Estatísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisitos
<a name="BKMK_Requirements"> </a>

Você precisará considerar os seguintes requisitos de hardware, software e rede antes de implantar o Gerenciador de estatísticas.

### <a name="software-requirements"></a>Requisitos de software

- Windows Server 2012 R2

- IIS (instalado automaticamente)

- Relacionada

- Serviços do Gerenciador de estatísticas (instalados automaticamente)

- PSExec - necessário para fazer a implantação do agente remoto

- .NET 4.5 (incluído no 2012 R2) - necessário para agentes e componentes de servidor

### <a name="networking-requirements"></a>Requisitos de rede


|**Servidor de hospedagem**|**Agentes**|**Ouvinte**|
|:-----|:-----|:-----|
|Rede de gigabit mínimo full-duplex.  <br/> |Porta TCP de saída 8443 (número de porta personalizável) para se comunicar com o ouvinte.  <br/> |A porta de escuta deve ser o mesmo em todos os servidores.  <br/> |
|A porta TCP 80 ou 443 open para hospedar o site de entrada.  <br/> |||
|Porta TCP 8443 (número de porta personalizável) de entrada para os agentes de se comunicar com ele.  <br/> |||

Durante a instalação, portas de firewall para o ouvinte e o site da Web são criadas automaticamente. Para os agentes, a instalação pressupõe que as conexões TCP de saída são permitidas por padrão.

### <a name="hardware-requirements"></a>Requisitos de hardware

Em uma implantação local, em que um único servidor hospeda todos os componentes do Gerenciador de estatísticas do servidor, um servidor com 16 GB de RAM e 4 CPU deve ser capaz de suportar cerca de 150 amostras por segundo em média. Para determinar quantos contadores/agentes que você pode oferecer suporte, use o seguinte cálculo:

100 servidores \*80 contadores \* 1 amostra por minuto de cada agente / 60 segundos = ~ 133 amostras por segundo.

## <a name="security-considerations"></a>Considerações de segurança
<a name="BKMK_Security"> </a>

Todo o tráfego entre os servidores é criptografado.

- Tráfego HTTPS criptografado será enviado através da porta 8443 (por padrão) do agente para o servidor de ouvinte.

- O agente verificará a impressão digital SSL no servidor para garantir que o servidor de ouvinte é o destinatário esperado. Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia). Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.

- Depois que o agente está satisfeito o ouvinte é autêntico, uma senha será apresentada pelo agente que depois é verificado pelo ouvinte.

- O agente começa a transmissão de dados de desempenho pela conexão ao ouvinte.

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Security"> </a>

Para obter mais informações, consulte:

- [Implantar o Gerenciador de estatísticas para Skype para Business Server](deploy.md)

- [Atualizar o Gerenciador de estatísticas para Skype para Business Server](upgrade.md)

- [Solucionar problemas de gerente de estatísticas para Skype para Business Server](troubleshoot.md)

- [Blog sobre o Gerenciador de Estatísticas do Skype for Business Server](https://blogs.technet.microsoft.com/skypestatsman/)


