---
title: Planejar o Gerenciador de estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumo: Leia este tópico para saber mais sobre o Gerenciador de estatísticas do Skype for Business Server.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816230"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planejar o Gerenciador de estatísticas do Skype for Business Server

**Resumo:** Leia este tópico para saber mais sobre o Gerenciador de estatísticas do Skype for Business Server.

 O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir o desempenho e a integridade do Skype for Business Server em tempo real. É possível sondar dados de desempenho em centenas de servidores em intervalos de alguns segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.

Você pode usar o Gerenciador de estatísticas para identificar problemas de desempenho contínuos, Ver os resultados de uma alteração planejada em seu ambiente, acompanhar a resolução de paralisações e muito mais. A partir da caixa, o Gerenciador de estatísticas é configurado com os principais limiares do Key Health Indicator (KHI) e pode ser personalizado para atender às necessidades exclusivas da sua implantação.

Você pode implantar o Gerenciador de estatísticas em uma implantação local na qual um único servidor hospeda todos os componentes do Gerenciador de estatísticas do lado do servidor. Para obter mais informações sobre a implantação do Gerenciador de estatísticas, consulte [implantar o Gerenciador de estatísticas para o Skype for Business Server](deploy.md). Se você já tiver uma implantação existente do Gerenciador de estatísticas, mas ainda não atualizou para o lançamento do 2,0, Confira as novidades [na versão 2,0 e o](plan.md#BKMK_WhatsNew) [Gerenciador de estatísticas de atualização para o Skype for Business Server](upgrade.md).

Este tópico inclui as seguintes seções:

- [Recursos e funcionalidades](plan.md#BKMK_Features)

- [O que há de novo no lançamento 2,0](plan.md#BKMK_WhatsNew)

- [Componentes](plan.md#BKMK_Components)

- [Implantação local](plan.md#BKMK_DeploymentOptions)

- [Requisitos](plan.md#BKMK_Requirements)

- [Considerações de segurança](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Recursos e funcionalidades
<a name="BKMK_Features"> </a>

O Gerenciador de estatísticas permite que você:

- Exiba dados brutos para todos os servidores em tempo real. (Os dados são amostrados a uma taxa muito alta e enviados para o website em menos de um segundo.)

- Exibir dados agregados para uma função específica; por exemplo, servidor front-end, servidor de mediação, servidor de borda e assim por diante.

- Faça drill down para exibir dados de sites específicos, pools específicos dentro do site e, em seguida, servidores específicos dentro do pool.

- Crie gráficos personalizados para que os contadores escolhidos sejam mostrados por padrão.

- Aplicar zoom e panorâmica nos eixos x e y ou somente no eixo x.

- Use intervalos de datas ou pontos no tempo para filtrar dados.

- Exibir o desempenho do servidor com base em indicadores chave de integridade estabelecidos (KHIs). KHIs representa uma coleção de contadores de desempenho com um intervalo saudável definido.

- Exiba métricas detalhadas para cada contador.

- Comparar dados em várias populações ou servidores.

- Exiba relatórios de contador latentes para identificar agentes que não estão relatando dados atuais para o serviço de painel.

- Salvar uma instância específica de dados de gráfico em um arquivo.

- Exiba KHIs em tempo real, incluindo atualizações. Se a exibição do histórico estiver habilitada, apenas novas falhas serão exibidas.

  - Exibir todas as KHIs ao mesmo tempo

  - Exibir KHIs por servidor (modo de exibição paisagem)

  - Exibir definições KHI

## <a name="whats-new-in-release-20"></a>O que há de novo no lançamento 2,0
<a name="BKMK_WhatsNew"> </a>

Veja a seguir as novidades da versão 2,0. Se você tiver uma implantação existente do Gerenciador de estatísticas e ainda não tiver atualizado, consulte [Gerenciador de estatísticas de atualização para o Skype for Business Server](upgrade.md).

- Os modos de exibição de cenário foram adicionados para mídia de borda, integridade da malha, failover de pool e cenários de registro.

- Muitos novos contadores foram adicionados para SQL Servers, mais contadores de uso do Skype for Business e assim por diante.

- Integração do nó do inspetor para o agente do Gerenciador de estatísticas-se o agente estiver instalado em um nó do Inspetor, ele reportará as estatísticas de transação sintética como contadores de volta para o Gerenciador de estatísticas.

- Diversas melhorias de confiabilidade e desempenho.

Para verificar a versão do site do Gerenciador de estatísticas que você está executando:

- No explorador de arquivos, abra (diretório padrão) C:\Program Files\Skype for Business Server stats WebSite\bin

- Clique com o botão direito do mouse em StatsManHubWebSite. dll e veja suas propriedades

- A versão do produto será mostrada nos detalhes de Descrição.

## <a name="components"></a>Componentes
<a name="BKMK_Components"> </a>

O Gerenciador de estatísticas consiste nos seguintes componentes:

- **Agente.** Um agente leve que é executado em cada servidor monitorado. O agente permite a sondagem de taxa alta configurável de contadores de desempenho com agregação local.

- **Ouvinte.** A API do lado do servidor que recebe dados de todos os agentes e agrega dados em populações.

- **Borda.** Funciona como a API do cliente para o sistema, é executada no (s) servidor (es) da Web e fornece atualizações de dados em tempo real para os clientes conectados pelo website. (O Hub é instalado automaticamente como parte do MSI do site.)

- **Site.** Uma interface de usuário que reúne todos os recursos disponíveis no sistema.

Além disso, o Gerenciador de estatísticas requer o **Redis**, um servidor de estrutura de dados aberto em cache para cache na memória. Para obter mais informações sobre como baixar o Redis, consulte [implantar o Gerenciador de estatísticas](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Implantação local
<a name="BKMK_DeploymentOptions"> </a>

Em uma implantação local, um único servidor hospeda todos os componentes do Gerenciador de estatísticas do lado do servidor.

O diagrama a seguir mostra uma implantação local, na qual o site do Gerenciador de estatísticas, o Hub, o ouvinte e o sistema de cache do Redis são hospedados em uma única máquina. O Gerenciador de estatísticas está monitorando três servidores do Skype for Business, cada um com um único agente que transmite dados para o ouvinte. Os usuários se conectam a um único site para exibir todos os dados agregados pelo Gerenciador de estatísticas:

![Implantação do Gerenciador de estatísticas local](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisitos
<a name="BKMK_Requirements"> </a>

Você precisará considerar os requisitos de software, rede e hardware a seguir antes de implantar o Gerenciador de estatísticas.

### <a name="software-requirements"></a>Requisitos de software

- Windows Server 2016 e 2019

- IIS (instalado automaticamente)

- Redis

- Serviços do Gerenciador de estatísticas (instalado automaticamente)

- PSExec-necessário para a implantação de agente remoto

- .NET 4,5 (incluído no 2012 R2)-necessário para agentes e componentes do lado do servidor
- Baixar o [Skype for Business Server, Gerenciador de estatística em tempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisitos de rede


|**Servidor de hospedagem**|**Agentes**|**Ouvinte**|
|:-----|:-----|:-----|
|Rede mínima Gigabit Full duplex.  <br/> |Porta TCP de saída 8443 (número da porta personalizável) para se comunicar com o ouvinte.  <br/> |A porta do ouvinte deve ser igual em todos os servidores.  <br/> |
|Entrada de porta TCP 80 ou 443 aberta para hospedar o site.  <br/> |||
|Porta TCP de entrada 8443 (número de porta personalizável) dos agentes para se comunicar com ele.  <br/> |||

Durante a instalação, as portas do firewall para o ouvinte e o site são criadas automaticamente. Para os agentes, a instalação pressupõe que conexões TCP de saída são permitidas por padrão.

### <a name="hardware-requirements"></a>Requisitos de hardware

Em uma implantação local, na qual um único servidor hospeda todos os componentes do Gerenciador de estatísticas do lado do servidor, um servidor com 16 GB de RAM e 4 CPUs deve ser capaz de dar suporte a 150 exemplos por segundo, em média. Para determinar a quantos contadores/agentes você pode dar suporte, use o seguinte cálculo:

servidores \*do 100 80 \* contadores 1 amostra por minuto de cada agente/60 segundos = ~ 133 amostras por segundo.

## <a name="security-considerations"></a>Considerações de segurança
<a name="BKMK_Security"> </a>

Todo o tráfego entre servidores é criptografado.

- O tráfego HTTPS criptografado será enviado pela porta 8443 (por padrão) do agente para o servidor de ouvinte.

- O agente verificará a impressão digital SSL no servidor para garantir que o servidor de ouvintes seja o destinatário esperado. Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia). Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.

- Depois que o agente estiver satisfeito, o ouvinte será autêntico, uma senha será apresentada pelo agente que então será verificado pela escuta.

- O agente começa a transmitir dados de desempenho pela conexão com o ouvinte.

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Security"> </a>

Para obter mais informações, consulte o seguinte:

- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)

- [Atualizar o Gerenciador de estatísticas do Skype for Business Server](upgrade.md)

- [Solução de problemas do Gerenciador de estatísticas do Skype for Business Server](troubleshoot.md)
