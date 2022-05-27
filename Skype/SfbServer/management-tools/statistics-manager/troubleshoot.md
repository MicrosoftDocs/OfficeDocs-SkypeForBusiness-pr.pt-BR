---
title: Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumo: Leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas para Skype for Business Server.'
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675273"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server

**Resumo:** Leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas para Skype for Business Server.

Este tópico descreve como solucionar problemas de implantação do Gerenciador de Estatísticas descrevendo eventos que você pode ver no log de eventos do aplicativo e as ações apropriadas que você pode tomar para corrigir o evento. Este tópico contém as seguintes seções:

- [Eventos do agente](troubleshoot.md#BKMK_Agent)

- [Eventos de ouvinte](troubleshoot.md#BKMK_Listener)

- [Problemas de site](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>Eventos do agente
<a name="BKMK_Agent"> </a>

- **1000** — Não é possível configurar o limitador do processador (Objeto de Trabalho) — Motivo desconhecido

- **1001** – A limitação do processo não é permitida no processo (provavelmente já está dentro de um objeto de trabalho)

    O Agente é executado dentro de um objeto Windows trabalho para limitar automaticamente seu volume de memória. Se o agente não for iniciado e essas entradas de evento estiverem presentes no log de eventos, o Objeto de Trabalho não poderá ser instanciado no servidor. Para contornar isso, o limite de memória superior pode ser removido alterando um valor no arquivo de configuração:

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Pesquise "MaxProcessMemoryMB" e altere o valor para "0", conforme mostrado:

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se essa alteração for feita, o Agente \< geralmente ainda consumirá 100 MB de memória, no entanto, ele não será forçado a 300 MB, como é o padrão. Se essa alteração for feita, recomendamos monitorar de perto o uso de memória para garantir que o Agente não consuma uma grande quantidade de memória em seu computador host.

- **2000** – Falha na inicialização do cliente

- **2001** – Não foi possível fazer nenhuma conexão com o serviço em qualquer IP de origem

  Se o Agente não puder se conectar ao computador ouvinte, verifique o seguinte:

  1. Verifique se o serviço Ouvinte está em execução no computador ouvinte. Caso contrário, verifique se o Redis está em execução no servidor e reinicie o serviço Ouvinte.

     Verifique o log de eventos do Gerenciador de Estatísticas no computador ouvinte para garantir que não haja problemas com o próprio serviço ouvinte do Gerenciador de Estatísticas.

  2. Use uma ferramenta de conectividade, como telnet, para verificar a conectividade do computador do Agente com o Ouvinte na porta correta.

     Caso contrário, verifique se a regra de firewall de entrada está habilitada no computador ouvinte para o tipo de rede ao qual o computador ouvinte está conectado (privado/público/domínio). Se o computador ouvinte não estiver ingressado em um domínio, a rede poderá ser listada como pública e, nesse caso, as regras de firewall instaladas com o Gerenciador de Estatísticas não serão aplicadas por padrão.

- **4000** – Falha ao baixar informações do servidor do ouvinte (motivo desconhecido)

  - **4001** — Servidor não encontrado na topologia do ouvinte

    Esse erro ocorrerá se o servidor estiver se conectando com êxito ao Ouvinte, mas o servidor não tiver sido adicionado à topologia no cache do Ouvinte. Opções de resolução:

  - Verifique se você seguiu as instruções para importar a topologia. Consulte [Importar a topologia](deploy.md#BKMK_ImportTopology).

  - Se o Agente estiver em um servidor que não esteja listado na topologia (por exemplo, os nós em um cluster AlwaysOn do SQL), você precisará adicionar o Agente manualmente seguindo as instruções em Importar a [topologia](deploy.md#BKMK_ImportTopology).

  - **4002** — Senha de ouvinte inválida

    A senha criptografada que o agente está tentando usar não corresponde à senha de serviço no próprio Ouvinte. Desinstale o Agente e reinstale-o usando a senha de serviço correta.

  - **4003** – Incompatibilidade de impressão digital do certificado

    A impressão digital do certificado fornecida ao Agente no momento da instalação não corresponde à impressão digital no certificado que o Ouvinte está usando no momento e, portanto, a conexão será recusada. Desinstale o Agente e reinstale-o usando a impressão digital correta do certificado.

  - **4004** — Resposta inválida ou HttpStatusCode

    O Ouvinte não está respondendo com um status esperado.

  - Se a conexão for proxida, verifique a configuração do proxy.

  - Verifique o log statsMan do computador ouvinte em caso de problemas com sua configuração.

  - **4005** – Não foi possível des serializar o XML

    As informações do servidor no servidor ouvinte estão corrompidas ou pode haver uma incompatibilidade de versão entre o Agente e os computadores ouvintes. Verifique se as versões correspondem e verifique se há problemas no log de eventos do Ouvinte.

## <a name="listener-events"></a>Eventos de ouvinte
<a name="BKMK_Listener"> </a>

- **10000** – Falha na inicialização Motivo desconhecido (eles são irrecuperáveis e o serviço será interrompido/falhará como resultado)

  - **10001** — Problema de configuração

    Geralmente, isso ocorrerá quando o arquivo [listener_install_location]\PerfAgentListener.exe.config tiver sido modificado manualmente e não puder ser lido pelo aplicativo.

  - **10002** – Erro de inicialização do ouvinte HTTP

    Esse evento geralmente será registrado quando a ACL de URL não tiver sido definida corretamente durante a instalação ou o Certificado SSL for inválido. Verifique se o certificado em sua configuração é válido. Se estiver, reinstale o Ouvinte de acordo com as instruções no [Gerenciador de Estatísticas de Implantação](deploy.md#BKMK_Deploy).

  - **10003** – Falha do Redis

  - **10004** – falha Caching infraestrutura

  - **10007** — Configurações (armazenado no redis)

    O ouvinte não pôde contatar o Redis nem recuperar dados bem formados do cache e não pôde iniciar. Verifique se o serviço Redis foi iniciado e configurado corretamente no servidor.

  - **10005** – Recuperação/análise de informações do servidor

    As informações de topologia no cache Redis são inválidas. Primeiro, tente reiniciar o Redis e o Ouvinte. Se o erro persistir, consulte [Importar a topologia](deploy.md#BKMK_ImportTopology) para recriar os dados de topologia.

- **10100** – Interrupção de PING do Redis

  - **10101** – Interrupção contínua do PING do Redis (a cada 60 segundos)

  - **30100** – Interrupção de PING do Redis restaurada

    Eles serão registrados quando o Ouvinte não puder se conectar ao Redis. Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.

- **10200** – Interrupção de gravação do Redis

  - **10201** – Interrupção de gravação do Redis continuada (a cada 60 segundos)

  - **30100** – Interrupção de gravação do Redis resolvida

    Eles serão registrados quando o Ouvinte não puder gravar no cache Redis. Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.

- **30000** – Iniciado com êxito

    Registrado sempre que o Ouvinte é iniciado.

- **22000** – Inicialização do Agente do Gerenciador de Estatísticas bem-sucedida.

- **23000** – Inicialização de EventLogQueryManager bem-sucedida (primeira vez ou após falha)

- **24000** — Inicialização de serverinfo bem-sucedida (primeira vez ou após falha)

- **25000** – O ouvinte está novamente online após não conseguir postar (ou a primeira postagem bem-sucedida)

- **5000** – Início do ouvinte offline para postar dados

- **5001** – O ouvinte ainda está offline por um período estendido

    Esses eventos podem ser úteis para monitorar/alertar/limpar problemas.

## <a name="website-issues"></a>Problemas de site
<a name="BKMK_Website"> </a>

- Prompts de logon repetitivos no Chrome – esse foi um bug que foi resolvido na versão 1.1. Verifique se você atualizou para a versão mais recente do Gerenciador de Estatísticas se estiver vendo prompts de logon repetidos no navegador Chrome. Para verificar a versão do site que você está executando:

  - No Explorador de Arquivos, abra (diretório padrão)

  - Clique com o botão direito StatsManHubWebSite.dll e exiba suas propriedades.

  - Se um computador não puder ser encontrado no modo de exibição Paisagem khi ou no modo de exibição Detalhes do Contador, verifique se ele é membro de um Site e de um Pool. Caso contrário, ele não aparecerá nesses modos de exibição. Para obter informações sobre como definir um site e pool para um servidor na topologia, [consulte Importar a topologia](deploy.md#BKMK_ImportTopology).

  - A versão do produto será mostrada nos detalhes da Descrição.

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Website"> </a>

Para obter mais informações, confira o seguinte:

- [Planejar o Gerenciador de estatísticas do Skype for Business Server](plan.md)

- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)

- [Atualizar o Gerenciador de estatísticas do Skype for Business Server](upgrade.md)
