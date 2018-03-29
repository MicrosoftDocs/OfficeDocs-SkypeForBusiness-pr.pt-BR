---
title: Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a>Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype
 
Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.
  
## <a name="administrative-portal"></a>Portal Administrativo

Para Skype para implantações em instalações de Business Server, você pode usar o portal do sistema de sala Skype administrativo ativamente gerenciar e monitorar implantações de sistemas de sala Skype dentro da sua organização.
  
Consulte os seguintes artigos para obter mais detalhes:
  
- [Implantando o Portal de Web administrativo do sistema de sala do Lync no Lync Server 2013](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [Configurando o seu ambiente do Lync Server 2013 para o Lync sala sistema administrativas Portal da Web](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [Instalando o Portal de Web administrativo do sistema de sala do Lync no Lync Server 2013](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [Usando o Portal de Web administrativo do sistema de sala do Lync no Lync Server 2013](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Sistema de sala Skype podem ser monitorado por meio do System Center Operations Manager (SCOM) baixando o [Pacote de gerenciamento de sistema do Skype sala](https://www.microsoft.com/en-us/download/details.aspx?id=42320) e instalá-lo em seu servidor SCOM. Você pode usar o SCOM para definir alertas, monitorar a integridade do sistema do Skype sala, gerar relatórios de tempo de atividade e muito mais. Sistema de sala do Skype vem com um agente de monitoramento pré-instaladas que pode ser configurado para apontar para o servidor SCOM. Consulte o guia de instalação fornecido pelo fabricante do seu sistema de sala Skype para saber como configurar o agente de monitoramento no sistema de sala do Skype.
  
## <a name="exchange-checklist"></a>Verificação do Exchange

- O item Confirmar a Descoberta Automática é configurado e um DNS A/CNAME RECORD está disponível para autodiscover.domain.com.
    
- Executar o ping de descoberta automática (por exemplo, Ping Autodiscover.contoso.com).
    
- Teste seu serviço de Descoberta Automática com a Ferramenta de Análise de Conectividade da Microsoft. Escolha o primeiro teste, "Eu não pode fazer logon com o Office Outlook".
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o sistema de sala Skype (script de exemplo na parte inferior da página).
    
## <a name="skype-for-business-checklist"></a>Skype para a lista de verificação de negócios

- Executar as seguintes ferramentas:
    
  - Skype para negócios Best Practices Analyzer 
    
  - Skype para ferramenta de análise de integridade comercial (Excel) 
    
  - Skype para o analisador de conectividade de negócios, 32 bits ou 64 bits
    
- Examine a [solução de problemas novo útil e ferramentas de análise para o Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Confirme que você tem um Skype para pool de negócios e um servidor de Office Web Apps e pode compartilhar um deck de PowerPoint usando o Skype para clientes corporativos.
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, você deve ativá-lo para Skype para negócios.
    
- Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.
    
## <a name="network"></a>Rede

- Verifique se que você tem uma conexão de rede com fio para o sistema de sala Skype.
    
- Leia a guia de planejamento para Skype para negócios de rede.
    
- Solicite uma Skype para avaliação da rede de negócios de uma Skype para parceiro de negócios.
    
- Ler os dados de desempenho capturados no Skype para ferramenta de análise de integridade comercial (Excel).
    
- Execute a Ferramenta de Análise de Rede.
    
- Execute a Ferramenta de Pré-diagnóstico de chamada.
    
## <a name="skype-room-system-security"></a>Segurança do sistema de sala do Skype

Sistema de sala Skype é um sistema de incorporado que pode ser totalmente integrado em uma implantação do Windows, usando o Skype para o modelo de segurança de negócios, gerenciamento de direitos e ferramentas de gerenciamento, como o SCOM. Os recursos incluem:
  
- Um Filtro de Gravação para impedir gravações de disco no modo usuário 
    
- Bloqueador de aplicativos para impedir que aplicativos não autorizados sejam executados. Todas as portas USB estão desabilitadas no modo usuário.
    
  - Nenhum apps standard ou visualizadores residem no hardware do sistema de sala Skype. Todo o conteúdo é processado por meio de protocolos HTTP ou RDP.
    
  - O PC executa o sistema operacional Padrão 7 Incorporado do Windows. Todo o hardware, incluindo dispositivos, é fornecido pelos parceiros de OEM.
    
  - Ingresso Opcional de Domínio para Serviços de Domínio do Active Directory (AD DS), permitindo gerenciamento e controle de contas de segurança local.
    
- Você também pode gerenciar a conta de administrador local usando o Skype para centro de administração de negócios.
    
- Sistema de sala Skype for atualizado por meio de processos padrão do Microsoft Update.
    
- Sistema de sala Skype conecta-se com Skype para negócios.
    
  - Skype para negócios usa criptografia de ponta a ponta e autorização para todos os modos de comunicação
    
  - Sistema de sala Skype suporta Skype para padrões de segurança e conformidade de negócios. Consulte Planejamento de segurança no Lync Server 2013 para obter mais informações.
    
## <a name="license"></a>Licença

Verify that you use a KMS for activating software. Nesse caso, você talvez precisem verificar ou adicionar o Skype para a chave KMS do cliente de negócios a ela. Se você não estiver usando o KMS, em seguida, solicite o chave de licenciamento para o Skype para o cliente de negócios MAK por volume.
  
## <a name="license-keys"></a>Chaves de Licença

Skype sala sistema executa o Skype para o cliente de desktop de negócios em segundo plano. Se o sistema de sala do Skype é um membro do domínio, ele descobre seu KMS. (Se houver a chave Lync KMS de Licenciamento de Volume, ela será ativada automaticamente). O Licenciamento do Volume também oferece um MAK, que você digita quando ele exibe xxxxx-xxxxx-xxxxx-xxxxx. (Você precisa ter acesso à Internet para ativar utilizando o MAK, mas não o KMS). Para obter mais informações, consulte ativação do Volume do Office 2013.
  
- Para inserir a chave MAK, vá para configurações de OEM \> SRS Licensing Tool. Clique em Verificar Estado. Quando o status diz "produto não está ativado", digite a chave.
    
- Se durante a ativação, você receber um erro que diz, "' o serviço de licenciamento de Software relatou que a chave do produto é inválida," Verifique se que:
    
  - A chave foi inserida corretamente.
    
  - Você inseriu o Skype para chave MAK de negócios e não outra chave.
    
  - O sistema tem acesso à Internet.
    
- Você pode ativá-lo por telefone, mas deve tentar ativá-lo usando primeiramente a Ferramenta de Licenciamento de SRS. Para ativá-lo por telefone, inicie uma reunião de teste (não uma chamada de teste, pois ela é muito curta). No Assistente de ativação do Office, selecione a ativação por telefone, ligue para a Microsoft, digite o número longo e digite uma resposta.
    
## <a name="certificate-authority"></a>Autoridade de Certificação

Confirme se a Autoridade de Certificação utilizada para emitir o certificado do Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade de Listas de Revogação de Certificados.
  
Importe o arquivo de certificado (. crt) para o sistema de sala Skype se estiver usando o Skype para Business Server. Pode ser facilmente obtido no compartilhamento CertEnroll do servidor CA ou na pasta Raiz Confiável de qualquer PC que participe do domínio.
  
## <a name="certificates"></a>Certificados

Verifique se sua Autoridade de Certificação tem um caminho de http para a lista de Revogação de Certificados. Se não tiver, atualize a sua CA para incluir um.
  
Instalar certificados na configuração do administrador do sistema Skype sala em configurações do sistema \> Gerenciador de certificados. Você precisa de um CA de Raiz Corporativa para seu certificado interno.
  
Uma maneira de obter os certificados que você precisa consiste em descobrir a CA que emitiu seus certificados. Skype para Business Server, em um PC em Skype para a empresa, clique em configurações \> ferramentas \> configurações de conferência discada. Esta opção abrirá uma página da web protegida pelo nome de CA que emitiu os certificados internos do Lync. Clique no ícone de Cadeado na barra de endereço do navegador para exibir um relatório de segurança. Clique em Exibir Certificados e examine a propriedade do Ponto de Distribuição de CRL. O segundo parâmetro de CN deve ser o nome do servidor de CA. Abra o Windows Explorer para esse endereço agora \\ \< nome do servidor CA \>\CertEnroll. Copie o dois arquivos .crl e o arquivo .crt em uma unidade flash e coloque-os no lado esquerdo da placa SMART.
  
Importe o arquivo. CRT para o sistema de sala Skype sob a pasta autoridades de certificação da sala.
  
Importe os arquivos. CRL no sistema de sala Skype sob a pasta autoridades de certificação intermediários. (Será necessário alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para visualizar os arquivos.)
  
Nota: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA do Lync. Caso contrário, você não poderá compartilhar PowerPoint em uma reunião. Verifique com o departamento de TI e permita que os arquivos CRT e CRL fora da rede de CA compartilhem CertEnroll como explicado acima. 
  
A associação de domínio pode simplificar algumas coisas porque você pode tratar o sistema de sala Skype como um sistema Windows, e ele pode depender do Active Directory para alguns dos aspectos de certificado. No entanto, é melhor gerenciar este assunto manualmente.
  

