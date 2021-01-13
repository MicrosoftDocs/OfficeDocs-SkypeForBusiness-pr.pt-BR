---
title: Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumo: Leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821771"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server
 
**Resumo:** Leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas do Skype for Business Server.
  
Este tópico descreve como solucionar problemas de implantação do Gerenciador de Estatísticas descrevendo os eventos que você pode ver no log de eventos do aplicativo e as ações apropriadas que você pode tomar para corrigir o evento. Este tópico contém as seguintes seções:
  
- [Eventos de agente](troubleshoot.md#BKMK_Agent)
    
- [Eventos de ouvinte](troubleshoot.md#BKMK_Listener)
    
- [Problemas do site](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventos de agente
<a name="BKMK_Agent"> </a>

- **1000** — Não é possível configurar o limitador de processador (Objeto de Trabalho) — Motivo desconhecido
    
- **1001** — A limitação do processo não é permitida no processo (provavelmente já está dentro de um Objeto de Trabalho)
    
    O Agente é executado dentro de um Objeto de Trabalho do Windows para limitar automaticamente seu espaço de memória. Se o agente não for iniciar e essas entradas de evento estão presentes no log de eventos, o Objeto de Trabalho não pode ser instanciado no servidor. Para resolver esse problema, o limite de memória superior pode ser removido alterando um valor no arquivo de configuração:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Procure "MaxProcessMemoryMB" e altere o valor para "0", conforme mostrado:
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se essa alteração for feita, o Agente geralmente ainda consumirá 100 MB de memória, no entanto, ele não será limitado a 300 MB como é o \< padrão. Se essa alteração for feita, recomendamos monitorar de perto o uso da memória para garantir que o Agente não consuma uma grande quantidade de memória em seu computador host. 
  
- **2000** — Falha de inicialização do cliente
    
- **2001**— Nenhuma conexão pode ser feita com o serviço em qualquer IP de origem
    
    Se o Agente não puder se conectar ao computador Ouvinte, verifique o seguinte:
    
    1. Certifique-se de que o serviço ouvinte está em execução no computador ouvinte. Se não estiver, verifique se o Redis está em execução no servidor e reinicie o serviço ouvinte.
        
        Verifique o log de eventos do Gerenciador de Estatísticas no computador Ouvinte para garantir que não haja problemas com o serviço Ouvinte do Gerenciador de Estatísticas em si.
        
    2. Use uma ferramenta de conectividade, como telnet, para verificar a conectividade do computador do Agente com o Ouvinte na porta correta.
        
        Caso não esteja, certifique-se de que a regra de firewall de entrada esteja habilitada no computador Ouvinte para o tipo de rede ao qual o computador Ouvinte está conectado (privado/público/domínio). Se o computador Ouvinte não for ingressado em um domínio, a rede poderá ser listada como pública e, nesse caso, as regras de firewall instaladas com o Gerenciador de Estatísticas não serão aplicadas por padrão.
    
- **4000** — Falha ao baixar informações do servidor do Ouvinte (motivo desconhecido)
    
  - **4001** — Servidor não encontrado na topologia do ouvinte
    
    Esse erro ocorrerá se o servidor estiver se conectando com êxito ao Ouvinte, mas o servidor não foi adicionado à topologia no cache do Ouvinte. Opções de resolução:
    
  - Certifique-se de seguir as instruções para importar a topologia. Consulte [Importar a topologia.](deploy.md#BKMK_ImportTopology) 
    
  - Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós em um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções em Importar a [topologia.](deploy.md#BKMK_ImportTopology)
    
  - **4002** — Senha de Ouvinte Inválida
    
    A senha criptografada que o agente está tentando usar não combina com a senha de serviço no Ouvinte em si. Desinstale o Agente e reinstale-o usando a senha de serviço correta.
    
  - **4003** — Incompatibilidade de impressão digital do certificado
    
    A impressão digital do certificado dada ao Agente no momento da instalação não combina com a impressão digital no certificado que o Ouvinte está usando no momento e, portanto, a conexão será recusada. Desinstale o Agente e reinstale-o usando a impressão digital correta do certificado.
    
  - **4004** — Resposta inválida ou HttpStatusCode
    
    O Ouvinte não está respondendo com um status esperado. 
    
  - Se a conexão for proxy, verifique a configuração do proxy.
    
  - Verifique o log statsMan do computador ouvinte em busca de problemas com sua configuração.
    
  - **4005** — Não foi preciso des serializar o XML
    
    As informações do servidor no servidor Ouvinte estão corrompidas ou pode haver uma incompatibilidade de versão entre o Agente e os computadores ouvintes. Verifique se as versões corresponderam e verifique se há problemas no log de eventos do Ouvinte.
    
## <a name="listener-events"></a>Eventos de ouvinte
<a name="BKMK_Listener"> </a>

- **10000** — Falha de inicialização Motivo desconhecido (eles são irrecuperáveis e o serviço irá parar/falhar como resultado)
    
  - **10001** — Problema de configuração
    
    Geralmente, isso ocorrerá quando o arquivo [listener_install_location]\PerfAgentListener.exe.config tiver sido modificado manualmente e não puder ser lido pelo aplicativo.
    
  - **10002** — Erro de inicialização do Ouvinte HTTP
    
    Esse evento geralmente será registrado quando a ACL da URL não tiver sido definida corretamente durante a instalação ou o Certificado SSL for inválido. Verifique se o certificado em sua configuração é válido. Se estiver, reinstale o Ouvinte de acordo com as instruções em [Implantar o Gerenciador de Estatísticas.](deploy.md#BKMK_Deploy)
    
  - **10003** — Falha do Redis
    
  - **10004** — Falha na infraestrutura de cache
    
  - **10007** – Configurações (armazenadas em redis)
    
    O Ouvinte não pôde contatar o Redis ou recuperar dados bem formados do cache e não pôde iniciar. Verifique se o serviço Redis foi iniciado e configurado corretamente no servidor.
    
  - **10005** — Recuperação/análise de informações do servidor
    
    As informações de topologia no cache redis são inválidas. Primeiro, tente reiniciar o Redis e o Ouvinte. Se o erro persistir, consulte [Importar a topologia para](deploy.md#BKMK_ImportTopology) recriar os dados de topologia.
    
- **10100** - Paralisação de PING do Redis
    
  - **10101** - Continuação da paralisação do PING do Redis (a cada 60 segundos)
    
  - **30100** — Paralisação de PING do Redis restaurada
    
    Eles serão registrados quando o Ouvinte não puder se conectar ao Redis. Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.
    
- **10200** - Redis Write outage
    
  - **10201** — Continuação da indisistção de gravação do Redis (a cada 60 segundos)
    
  - **30100** — Redis Write outage resolved
    
    Eles serão registrados quando o Ouvinte não puder gravar no cache do Redis. Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.
    
- **30000** – Iniciado com êxito
    
    Registrado sempre que o Ouvinte é iniciado.
    
- **22000** – Inicialização bem-sucedida do Agente do Gerenciador de Estatísticas.
    
- **23000** — Inicialização bem-sucedida do EventLogQueryManager (primeira vez ou após falha)
    
- **24000** — Inicialização bem-sucedida de serverinfo (primeira vez ou após falha)
    
- **25000** — O Ouvinte está novamente online após uma falha ao postar (ou primeira postagem bem-sucedida)
    
- **5000** — Início do ouvinte offline para postar dados
    
- **5001** — O Ouvinte ainda está offline por um longo período
    
    Esses eventos podem ser úteis para monitorar/alertar/limpar problemas.
    
## <a name="website-issues"></a>Problemas do site
<a name="BKMK_Website"> </a>

- Prompts de logon repetitivos no Chrome – um bug que foi resolvido na versão 1.1. Certifique-se de ter atualizado para a versão mais recente do Gerenciador de Estatísticas se estiver vendo prompts de logon repetidos no navegador Chrome. Para verificar a versão do site que você está executando:
    
  - No Explorador de Arquivos, abra (diretório padrão)
    
  - Clique com o botão direito do StatsManHubWebSite.dll e veja suas propriedades.
    
  - Se não for possível encontrar um computador na exibição Paisagem de KHI ou no de Detalhes do Contador, certifique-se de que ele seja membro de um Site e de um Pool. Se não estiver, ele não aparecerá nesses exibições. Para obter informações sobre como definir um site e pool para um servidor na topologia, consulte [Importar a topologia.](deploy.md#BKMK_ImportTopology)
    
  - A versão do produto será mostrada nos detalhes de Descrição.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Website"> </a>

Para obter mais informações, confira o seguinte:
  
- [Planejar o Gerenciador de estatísticas do Skype for Business Server](plan.md)
    
- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)
    
- [Atualizar o Gerenciador de estatísticas do Skype for Business Server](upgrade.md)
