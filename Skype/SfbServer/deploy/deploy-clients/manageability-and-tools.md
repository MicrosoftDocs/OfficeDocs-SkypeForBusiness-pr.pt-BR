---
title: Ferramentas e capacidade de gerenciamento do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para saber mais sobre as ferramentas de gerenciamento para o Sistema de Sala do Skype.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805791"
---
# <a name="skype-room-system-manageability-and-tools"></a>Ferramentas e capacidade de gerenciamento do Sistema de Sala do Skype
 
Leia este tópico para saber mais sobre as ferramentas de gerenciamento para o Sistema de Sala do Skype.
  
## <a name="administrative-portal"></a>Portal Administrativo

Para implantações locais do Skype for Business Server, você pode usar o portal administrativo do Sistema de Sala do Skype para gerenciar e monitorar ativamente as implantações do Sistema de Sala do Skype em sua organização.
  
Consulte o artigo a seguir para obter mais detalhes:
  
- [Implantar o Portal da Web Administrativo do SRS v1 no Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Lista de verificação do Exchange

- Confirme se a Descoberta Automática está configurada e um REGISTRO DNS A/CNAME interno está disponível para autodiscover.domain.com.
    
- Ping autodiscover (por exemplo, ping Autodiscover.contoso.com).
    
- Teste seu serviço de Descoberta Automática com a Ferramenta Analisador de Conectividade da Microsoft. Escolha o primeiro teste, "Não consigo fazer logoff com o Office Outlook".
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o Sistema de Sala do Skype (script de exemplo na parte inferior da página).
    
## <a name="skype-for-business-checklist"></a>Lista de verificação do Skype for Business

- Execute as seguintes ferramentas:
    
  - Analisador de Práticas Recomendadas do Skype for Business     
  - Ferramenta de Análise de Saúde do Skype for Business (Excel)    
  - Analisador de Conectividade do Skype for Business de 32 bits ou 64 bits
    
- Revise [as novas ferramentas úteis de solução de problemas e análise do Office 365.](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/) Confirme se você tem um pool do Skype for Business e um servidor do Office Web Apps e pode compartilhar um conjunto do PowerPoint usando o cliente Skype for Business.
    
- Se a sala de reunião já tiver uma caixa de correio de recursos, habilita-a para o Skype for Business.
    
- Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.
    
## <a name="network"></a>Rede

- Certifique-se de que você tenha uma conexão de rede com fio para o Sistema de Sala do Skype.
    
- Leia o Guia de Planejamento de Rede do Skype for Business.
    
- Solicite uma avaliação de rede do Skype for Business de um parceiro do Skype for Business.
    
- Leia os dados de desempenho capturados na Ferramenta de Análise de Saúde do Skype for Business (Excel).
    
- Execute a Ferramenta de Análise de Rede.
    
- Execute a Ferramenta de Diagnóstico de Pré-Chamada.
    
## <a name="skype-room-system-security"></a>Segurança do Sistema de Sala do Skype

O Sistema de Sala do Skype é um sistema incorporado que pode ser totalmente integrado em uma implantação do Windows, usando o modelo de segurança, gerenciamento de direitos e ferramentas de gerenciamento do Skype for Business, como o SCOM. Os recursos incluem:
  
- Um Filtro de Gravação para impedir gravações de disco no modo de usuário 
    
- App Locker para impedir a execução de aplicativos não autorizados. Todas as portas USB estão desabilitadas no modo de usuário.
    
  - Nenhum aplicativo padrão ou visualizadores residem no hardware do Sistema de Sala do Skype. Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.
    
  - O pc executa o sistema operacional Windows Embedded Standard 7. Todo o hardware, incluindo dispositivos, é fornecido por parceiros OEM.
    
  - O AD DS (Active Directory Domain Services) opcional permite o gerenciamento e o controle da conta de segurança local.
    
- Você também pode gerenciar a conta de administrador local usando o Centro de administração do Skype for Business.
    
- O Sistema de Sala do Skype é atualizado por meio de processos padrão do Microsoft Update.
    
- O Sistema de Sala do Skype se conecta ao Skype for Business.
    
  - O Skype for Business usa criptografia e autorização de ponta a ponta para todos os modos de comunicação
    
  - O Sistema de Sala do Skype dá suporte aos padrões de segurança e conformidade do Skype for Business. Consulte [Plano de segurança no Skype for Business Server](../../plan-your-deployment/security/security.md) para obter mais informações.
    
## <a name="license"></a>Licença

Verifique se você usa um KMS para ativar o software. Se for o caso, talvez seja necessário verificar ou adicionar a chave KMS do cliente Skype for Business a ela. Se você não estiver usando o KMS, solicite a chave de licenciamento por volume para a MAK do cliente Skype for Business.
  
## <a name="license-keys"></a>Chaves de licença

O Sistema de Sala do Skype executa o cliente de área de trabalho do Skype for Business em segundo plano. Se o Sistema de Sala do Skype for um membro do domínio, ele descobrirá seu KMS. (e se tiver a Chave KMS de Licenciamento por Volume, ela será ativada automaticamente). O Licenciamento por Volume também fornece uma MAK, que você ins dá ao exibir xxxxx-xxxxx-xxxxx-xxxxx. (Você precisa de acesso à Internet para ativar usando MAK, mas não KMS). Para obter mais informações, consulte a ativação de volume do Office 2013.
  
- Para inserir a chave MAK, vá para a Ferramenta de Licenciamento \> de SRS de Configurações OEM. Clique em Verificar Status. Quando o status diz "o produto não está ativado", insira a chave.
    
- Se durante a ativação você receber um erro que diz" "O Serviço de Licenciamento de Software relatou que a chave do produto é inválida", verifique se:
    
  - A chave foi inserida corretamente.
    
  - Você entrou na chave MAK do Skype for Business e não em outra chave.
    
  - O sistema tem acesso à Internet.
    
- Você pode ativar por telefone, mas deve ter tentado ativar usando primeiro a Ferramenta de Licenciamento do SRS. Para ativar por telefone, inicie uma reunião de teste (não uma chamada de teste, pois ela é muito curta). No Assistente de Ativação do Office, selecione Ativação de Telefone, ligue para a Microsoft, digite o número longo e insira uma resposta.
    
## <a name="certificate-authority"></a>Autoridade de Certificação

Confirme se a Autoridade de Certificação usada para emitir o certificado do Office Web Apps Server 2013 possui um caminho HTTP incluído na propriedade da Lista de Certificados Revogados.
  
Importe o arquivo de certificado (.crt) para o Sistema de Sala do Skype se estiver usando o Skype for Business Server. Ele é obtido facilmente do compartilhamento CertEnroll do servidor de CA ou na pasta Raiz Confiável de qualquer computador ingressado no domínio.
  
## <a name="certificates"></a>Certificados

Verifique se a Autoridade de Certificação tem um caminho http para a Lista de Revogação de Certificados. Caso não o seja, atualize sua AC para incluir uma.
  
Instale certificados na configuração administrativa do Sistema de Sala do Skype no Gerenciador de Certificados de Configurações \> do Sistema. Você precisa da AC raiz corporativa para seu certificado interno.
  
Uma maneira de obter os certificados necessários é descobrir a CA que emitiu seus certificados. Para o Skype for Business Server, em um computador no Skype for Business, clique em Configurações das Ferramentas de \> \> Conferência Discada. Isso abre uma página da Web protegida pela AC que emitiu os certificados internos. Clique no ícone Bloquear na barra de endereços do navegador para exibir um relatório de segurança. Clique em Exibir Certificados e examine a propriedade do Ponto de Distribuição da CRL. O segundo parâmetro CN deve ser o nome do servidor da AC. Agora abra o Windows Explorer para esse endereço \\ \< CA Server Name \> \CertEnroll. Copie os dois arquivos .crl e o arquivo .crt em uma unidade flash e coloque-os no lado esquerdo da placa SMART.
  
Importe o arquivo .crt para o Sistema de Sala do Skype na pasta Autoridade de Certificação de Sala Confiável.
  
Importe os arquivos .crl no Sistema de Sala do Skype na pasta Autoridades de Certificação Intermediárias. (Você precisa alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para ver os arquivos).
  
Observação: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA que o Skype for Business. Se isso não for feito, você não poderá compartilhar o PowerPoint em uma reunião. Verifique com a EQUIPE de IT e obtenha os arquivos CRT e CRL fora do compartilhamento de rede ca CertEnroll conforme explicado acima. 
  
A associação de domínio pode simplificar algumas coisas porque você pode tratar o Sistema de Sala do Skype como um sistema windows e ele pode depender do Active Directory para alguns dos aspectos do certificado. No entanto, é melhor gerenciar manualmente isso.
  

