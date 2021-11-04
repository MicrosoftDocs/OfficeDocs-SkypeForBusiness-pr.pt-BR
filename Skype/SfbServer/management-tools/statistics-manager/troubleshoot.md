---
title: Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumo: leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas para Skype for Business Server.'
ms.openlocfilehash: 3f3bade7c7696e7361b63dc2f539534b6072d34a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777301"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Solução de problemas do Gerenciador de Estatísticas do Skype for Business Server
 
**Resumo:** Leia este tópico para solucionar problemas de implantação do Gerenciador de Estatísticas para Skype for Business Server.
  
Este tópico descreve como solucionar problemas de implantação do Gerenciador de Estatísticas descrevendo eventos que você pode ver no log de eventos do aplicativo e as ações apropriadas que você pode tomar para corrigir o evento. Este tópico contém as seguintes seções:
  
- [Eventos de agente](troubleshoot.md#BKMK_Agent)
    
- [Eventos de ouvinte](troubleshoot.md#BKMK_Listener)
    
- [Problemas de site](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventos de agente
<a name="BKMK_Agent"> </a>

- **1000** — Não é possível configurar o limitador do processador (Objeto Job) — Motivo desconhecido
    
- **1001** — Limitação de processo não é permitida no processo (provavelmente já está dentro de um objeto Job)
    
    O Agente é executado dentro de um objeto de trabalho Windows para limitar automaticamente seu espaço de memória. Se o agente não for iniciar e essas entradas de evento estão presentes no log de eventos, o Objeto Job não poderá ser instaurou no servidor. Para resolver isso, o limite de memória superior pode ser removido alterando um valor no arquivo config:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Pesquise "MaxProcessMemoryMB" e altere o valor para "0" conforme mostrado:
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se essa alteração for feita, o Agente geralmente ainda consumirá 100 MB de memória, no entanto, ele não será limitado à força a 300 MB, como é o \< padrão. Se essa alteração for feita, recomendamos monitorar de perto o uso da memória para garantir que o Agente não consuma uma grande quantidade de memória em seu computador host. 
  
- **2000** — Falha na inicialização do cliente
    
- **2001**— Nenhuma conexão poderia ser feita ao serviço em qualquer IP de origem
    
    Se o Agente não puder se conectar ao computador Ouvinte, verifique o seguinte:
    
    1. Verifique se o serviço Ouvinte está sendo executado no computador Ouvinte. Caso não seja, verifique se o Redis está em execução nesse servidor e reinicie o serviço Ouvinte.
        
        Verifique o log de eventos do Gerenciador de Estatísticas no computador Ouvinte para garantir que não haja problemas com o serviço Ouvinte do Gerenciador de Estatísticas em si.
        
    2. Use uma ferramenta de conectividade, como telnet, para verificar a conectividade do computador Agente com o Ouvinte na porta correta.
        
        Caso não seja, certifique-se de que a regra de firewall de entrada esteja habilitada no computador Ouvinte para o tipo de rede ao qual o computador Ouvinte está conectado (privado/público/domínio). Se o computador Ouvinte não estiver ingressado em um domínio, a rede poderá ser listada como pública e, nesse caso, as regras de firewall instaladas com o Gerenciador de Estatísticas não serão aplicadas por padrão.
    
- **4000** — Falha ao baixar Informações do Servidor do Ouvinte (motivo desconhecido)
    
  - **4001** — Servidor Não Encontrado na Topologia do Ouvinte
    
    Esse erro ocorrerá se o servidor estiver se conectando com êxito ao Ouvinte, mas o servidor não foi adicionado à topologia no cache do Ouvinte. Opções de resolução:
    
  - Certifique-se de seguir as instruções para importar a topologia. Consulte [Importar a topologia](deploy.md#BKMK_ImportTopology). 
    
  - Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós em um cluster AlwaysOn do SQL), você precisará adicionar o Agente manualmente seguindo as instruções em Importar a [topologia](deploy.md#BKMK_ImportTopology).
    
  - **4002** — Senha de ouvinte inválida
    
    A senha criptografada que o agente está tentando usar não combina com a senha de serviço no próprio Ouvinte. Desinstale o Agente e reinstale-o usando a senha de serviço correta.
    
  - **4003** — Falha na impressão digital do certificado
    
    A impressão digital do certificado dada ao Agente no momento da instalação não corresponderá à impressão digital no certificado que o Ouvinte está usando no momento e, portanto, a conexão será recusada. Desinstale o Agente e reinstale-o usando a impressão digital correta do certificado.
    
  - **4004** — Resposta inválida ou HttpStatusCode
    
    O Ouvinte não está respondendo com um status esperado. 
    
  - Se a conexão for proxida, verifique a configuração do proxy.
    
  - Verifique se há problemas com a configuração do log statsMan do computador ouvinte.
    
  - **4005** — Não foi consegui desa serializar o XML
    
    As informações do servidor no servidor Ouvinte estão corrompidas ou pode haver uma incompatibilidade de versão entre os computadores Agent e Listener. Verifique se as versões corresponderam e verifique se há problemas no log de eventos Ouvinte.
    
## <a name="listener-events"></a>Eventos de ouvinte
<a name="BKMK_Listener"> </a>

- **10000** — Falha na inicialização Motivo desconhecido (eles são irrecuperáveis e o serviço interromperá/falhará como resultado)
    
  - **10001** — Problema de configuração
    
    Geralmente, isso ocorrerá quando o arquivo [listener_install_location]\PerfAgentListener.exe.config tiver sido modificado manualmente e não puder ser lido pelo aplicativo.
    
  - **10002** — Erro de inicialização do ouvinte HTTP
    
    Esse evento geralmente será registrado quando a URL ACL não tiver sido definida corretamente durante a instalação ou o Certificado SSL for inválido. Verifique se o certificado em sua configuração é válido. Se estiver, reinstale o Ouvinte de acordo com as instruções em [Deploy Statistics Manager](deploy.md#BKMK_Deploy).
    
  - **10003** — Falha de redis
    
  - **10004** — falha Caching infraestrutura
    
  - **10007** — Configurações (armazenado em redis)
    
    O Ouvinte não pôde contatar Redis ou recuperar dados bem formados do cache e não pôde iniciar. Verifique se o serviço Redis foi iniciado e configurado corretamente no servidor.
    
  - **10005** — Recuperação/análise de informações do servidor
    
    As informações de topologia no cache Redis são inválidas. Primeiro, tente reiniciar Redis e o Ouvinte. Se o erro persistir, consulte [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.
    
- **10100** — Redis PING outage
    
  - **10101** — Redis PING continua paralisação (a cada 60 segundos)
    
  - **30100** — A paralisação de PING redis foi restaurada
    
    Eles serão registrados quando o Ouvinte não puder se conectar ao Redis. Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.
    
- **10200** — Redis Write outage
    
  - **10201** — Redis Write outage continuada (a cada 60 segundos)
    
  - **30100** — Redis Write outage resolved
    
    Eles serão registrados quando o Ouvinte não puder gravar no cache Redis. Verifique se o Redis foi iniciado e se a conectividade de rede entre o Ouvinte e o Redis está disponível.
    
- **30000** — Iniciado com êxito
    
    Registrado sempre que o Ouvinte é iniciado.
    
- **22000** — A inicialização do Agente gerenciador de estatísticas foi bem-sucedida.
    
- **23000** — A inicialização de EventLogQueryManager foi bem-sucedida (primeira vez ou depois de falhar)
    
- **24000** — Inicialização de serverinfo bem-sucedida (primeira vez ou após falha)
    
- **25000** — Ouvinte está novamente online após não conseguir postar (ou primeira postagem bem-sucedida)
    
- **5000** — Início do ouvinte offline para postar dados
    
- **5001** — O ouvinte ainda está offline por um período estendido
    
    Esses eventos podem ser úteis para problemas de monitoramento/alerta/limpeza.
    
## <a name="website-issues"></a>Problemas de site
<a name="BKMK_Website"> </a>

- Prompts de logon repetitivos no Chrome - esse foi um bug que foi resolvido na versão 1.1. Certifique-se de que você atualizou para a versão mais recente do Gerenciador de Estatísticas se estiver vendo prompts de logon repetidos no navegador Chrome. Para verificar a versão do site que você está executando:
    
  - No Explorador de Arquivos, abra (diretório padrão)
    
  - Clique com o botão direito StatsManHubWebSite.dll e exibir suas propriedades.
    
  - Se um computador não puder ser encontrado no exibição Paisagem KHI ou no exibição Detalhes do Contador, certifique-se de que ele seja membro de um Site e de um Pool. Se não for, ele não aparecerá nesses exibições. Para obter informações sobre como definir um site e pool para um servidor na topologia, consulte [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - A versão do produto será mostrada nos detalhes de Descrição.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Website"> </a>

Para obter mais informações, confira o seguinte:
  
- [Planejar o Gerenciador de estatísticas do Skype for Business Server](plan.md)
    
- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)
    
- [Atualizar o Gerenciador de estatísticas do Skype for Business Server](upgrade.md)
