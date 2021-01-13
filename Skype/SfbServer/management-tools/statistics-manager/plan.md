---
title: Planejar o Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumo: Leia este tópico para saber mais sobre o Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821821"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planejar o Gerenciador de Estatísticas do Skype for Business Server

**Resumo:** Leia este tópico para saber mais sobre o Gerenciador de Estatísticas do Skype for Business Server.

 O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir dados de desempenho e de saúde do Skype for Business Server em tempo real. Você pode sondar dados de desempenho em centenas de servidores a cada poucos segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.

Você pode usar o Gerenciador de Estatísticas para identificar problemas de desempenho contínuos, exibir os resultados de uma alteração planejada em seu ambiente, controlar a resolução de paralisações e muito mais. O Gerenciador de Estatísticas está configurado com limites de KHI (Indicador Chave de Saúde) e pode ser personalizado de acordo com as necessidades exclusivas da sua implantação.

Você pode implantar o Gerenciador de Estatísticas em uma implantação local na qual um único servidor hospeda todos os componentes do Gerenciador de Estatísticas do lado do servidor. Para obter mais informações sobre como implantar o Gerenciador de Estatísticas, consulte [Implantar o Gerenciador de Estatísticas do Skype for Business Server.](deploy.md) Se você já tiver uma implantação existente do Gerenciador de Estatísticas, mas ainda não tiver atualizado para a versão 2.0, consulte Novidades na versão [2.0](plan.md#BKMK_WhatsNew) e Atualize o Gerenciador de Estatísticas do [Skype for Business Server.](upgrade.md)

Este tópico contém as seguintes seções:

- [Recursos](plan.md#BKMK_Features)

- [Novidades na versão 2.0](plan.md#BKMK_WhatsNew)

- [Componentes](plan.md#BKMK_Components)

- [Implantação no local](plan.md#BKMK_DeploymentOptions)

- [Requisitos](plan.md#BKMK_Requirements)

- [Considerações sobre segurança](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Recursos
<a name="BKMK_Features"> </a>

O Gerenciador de Estatísticas permite que você:

- Exibir dados brutos de todos os servidores em tempo real. (Os dados são amostrados a uma taxa muito alta e enviados ao site em menos de um segundo.)

- Exibir dados agregados para uma função específica; por exemplo, Servidor Front-End, Servidor de Mediação, Servidor de Borda e assim por diante.

- Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.

- Crie gráficos personalizados para que os contadores escolhidos sejam mostrados por padrão.

- Zoom and pan on both the x- and y- axes or on the x-axis only.

- Use intervalos de datas ou pontos no tempo para filtrar dados.

- Exibir o desempenho do servidor com base nos principais indicadores de saúde (KHIs) estabelecidos. KHIs representam uma coleção de contadores de desempenho com um intervalo almente definido.

- Exibir métricas detalhadas para cada contador.

- Compare dados entre várias populações ou servidores.

- Exibir relatórios de contador latentes para identificar agentes que não estão relatando dados atuais para o serviço de painel.

- Salve uma instância específica dos dados do gráfico em um arquivo.

- Exibir KHIs em tempo real, incluindo atualizações. Se o modo de exibição de histórico estiver habilitado, somente novas falhas serão exibidas.

  - Exibir todos os KHIs de uma só vez

  - Exibir KHIs por servidor (exibição paisagem)

  - Exibir definições de KHI

## <a name="whats-new-in-release-20"></a>Novidades na versão 2.0
<a name="BKMK_WhatsNew"> </a>

O exemplo a seguir descreve as novidades da versão 2.0. Se você tiver uma implantação existente do Gerenciador de Estatísticas e ainda não tiver atualizado, consulte Atualizar o Gerenciador de Estatísticas do [Skype for Business Server.](upgrade.md)

- As exibições de cenário foram adicionadas para cenários de Mídia de Borda, Fabric Health, Failover de Pool e Registro.

- Muitos contadores novos foram adicionados para servidores SQL, mais contadores de uso do Skype for Business e assim por diante.

- Integração do nó do watcher para o Agente do Gerenciador de Estatísticas - se o Agente estiver instalado em um nó do watcher, ele relatará estatísticas de transação sintética como contadores de volta para o Gerenciador de Estatísticas.

- Vários aprimoramentos de confiabilidade e desempenho.

Para verificar a versão do site do Gerenciador de Estatísticas que você está executando:

- No Explorador de Arquivos, abra (diretório padrão) C:\Arquivos de Programas\Skype for Business Server StatsMan WebSite\bin

- Clique com o botão direito do StatsManHubWebSite.dll e veja suas propriedades

- A versão do produto será mostrada nos detalhes de Descrição.

## <a name="components"></a>Componentes
<a name="BKMK_Components"> </a>

O Gerenciador de Estatísticas consiste nos seguintes componentes:

- **Agente.** Um agente leve que é executado em cada servidor monitorado. O Agente permite sondagem de alta taxa configurável de contadores de desempenho com agregação local.

- **Ouvinte.** A API do lado do servidor que recebe dados de todos os Agentes e agrega dados entre populações.

- **Hub.** Serve como a API do cliente para o sistema, é executado nos servidores Web e fornece atualizações de dados em tempo real para clientes conectados por meio do site. (O Hub é instalado automaticamente como parte do site msi.)

- **Site.** Uma interface do usuário que reúne todos os recursos disponíveis no sistema.

Além disso, o Gerenciador de Estatísticas requer **o Redis**, um servidor de estrutura de dados de código aberto para armazenamento em cache na memória. Para obter mais informações sobre como baixar o Redis, [consulte Implantar o Gerenciador de Estatísticas.](deploy.md#BKMK_Deploy)

## <a name="on-premises-deployment"></a>Implantação no local
<a name="BKMK_DeploymentOptions"> </a>

Em uma implantação local, um único servidor hospeda todos os componentes do Gerenciador de Estatísticas do lado do servidor.

O diagrama a seguir mostra uma implantação local, na qual o site do Gerenciador de Estatísticas, o Hub, o Ouvinte e o sistema de cache redis estão hospedados em um único computador. O Gerenciador de Estatísticas está monitorando três servidores do Skype for Business, cada um deles com um único Agente transmitindo dados para o Ouvinte. Os usuários se conectam a um único site para exibir todos os dados agregados pelo Gerenciador de Estatísticas:

![Implantação local do Gerenciador de Estatísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requirements
<a name="BKMK_Requirements"> </a>

Você precisará considerar os seguintes requisitos de software, rede e hardware antes de implantar o Gerenciador de Estatísticas.

### <a name="software-requirements"></a>Requisitos de software

- Windows Server 2016 e 2019

- IIS (instalado automaticamente)

- Redis

- Serviços do Gerenciador de Estatísticas (instalados automaticamente)

- PSExec - Necessário para fazer a implantação do agente remoto

- .NET 4.5 (incluído no 2012 R2) - Necessário para agentes e componentes do lado do servidor
- Baixar o [Skype for Business Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisitos de rede


|**Servidor de hospedagem**|**Agentes**|**Ouvinte**|
|:-----|:-----|:-----|
|Rede full duplex de gigabit mínima.  <br/> |Porta TCP de saída 8443 (número de porta personalizável) para se comunicar com o Ouvinte.  <br/> |A porta ouvinte deve ser a mesma em todos os servidores.  <br/> |
|Porta TCP de entrada 80 ou 443 aberta para hospedar o site.  <br/> |||
|Porta TCP de entrada 8443 (número da porta personalizável) para os agentes se comunicarem com ela.  <br/> |||

Durante a instalação, as portas de firewall para o Ouvinte e o Site são criadas automaticamente. Para os Agentes, a instalação supõe que as conexões TCP de saída são permitidas por padrão.

### <a name="hardware-requirements"></a>Requisitos de hardware

Em uma implantação local, na qual um único servidor hospeda todos os componentes do Gerenciador de Estatísticas do lado do servidor, um servidor com 16 GB de RAM e 4 CPU deve ser capaz de suportar cerca de 150 amostras por segundo em média. Para determinar quantos contadores/agentes você pode suportar, use o seguinte cálculo:

100 servidores 80 contadores 1 amostra por minuto de cada agente \* \* / 60 segundos = ~ 133 amostras por segundo.

## <a name="security-considerations"></a>Considerações de segurança
<a name="BKMK_Security"> </a>

Todo o tráfego entre servidores é criptografado.

- O tráfego HTTPS criptografado será enviado pela porta 8443 (por padrão) do Agente para o servidor Ouvinte.

- O Agente verificará a impressão digital SSL no servidor para garantir que o servidor Ouvinte seja o destinatário esperado. Observe que o Agente usa a verificação de impressão digital do certificado (em vez de verificação em cadeia). Ele não fará a validação completa do certificado porque é possível usar certificados auto-assinados.

- Depois que o Agente estiver satisfeito com a autenticidade do Ouvinte, uma senha será apresentada pelo Agente que, em seguida, será verificada pelo Ouvinte.

- O Agente começa a transmitir dados de desempenho pela conexão com o Ouvinte.

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Security"> </a>

Para obter mais informações, confira o seguinte:

- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)

- [Atualizar o Gerenciador de estatísticas do Skype for Business Server](upgrade.md)

- [Solução de problemas do Gerenciador de estatísticas do Skype for Business Server](troubleshoot.md)
