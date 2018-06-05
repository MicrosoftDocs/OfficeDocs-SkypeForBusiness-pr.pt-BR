---
title: Revisar os relatórios do administrador no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Os Relatórios de Administrador são informações detalhadas para implantações e operações. Os relatórios são gerados com base nas suas seleções marcadas em Sites de Design. O designer pode adicionar mais valor aos Relatórios de Administrador editando os diagramas de rede e definindo os endereços IP completos e os FQDNs (nome de domínio totalmente qualificado) para servidores, pools e balanceadores de carga.
ms.openlocfilehash: 1d2cea3b1e0b4e19192f19734b2dcd278ca8a38b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504758"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Revisar os relatórios do administrador no Skype for Business Server 2015
 
Os Relatórios de Administrador são informações detalhadas para implantações e operações. Os relatórios são gerados com base nas seleções marcadas em **Criar Locais**. O designer pode adicionar mais valor aos Relatórios de Administrador editando os diagramas de rede e definindo os endereços IP completos e os FQDNs (nome de domínio totalmente qualificado) para servidores, pools e balanceadores de carga.
  
O recurso Relatórios do administrador permite:
  
- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)
    
- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)
    
- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)
    
- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)
    
## <a name="review-the-summary-report"></a>Analisar o relatório de resumo
<a name="Summary_report"> </a>

O Skype para relatório do administrador de negócios é o primeiro de quatro relatórios valiosos que Documente seu design detalhadamente. As informações desse relatório, e dos outros três relatórios associados, são úteis para suas Equipes de Tecnologia da Informação:
  
![Relatório do administrador de resumo geral](../../media/General_Summary_Report_Admin_Report.png)
  
O Relatório de Resumo lista as informações gerais de configuração associadas à sua rede de Borda. O local, o FQDN (nome de domínio totalmente qualificado) e endereço IP, o tipo de rede e os comentários específicos a uma determinada função são documentados.
  
O designer e cada equipe que for implantar, gerenciar e manter a infraestrutura deve rever o relatório de resumo para obter precisão e garantir que ocorra o mínimo de erros.
  
Você também pode visualizar relatórios mais detalhados:
  
- Relatórios de certificados
    
- Relatório de firewall
    
- Relatório de DNS
    
## <a name="review-the-certificates-report"></a>Revisar o relatório de certificados
<a name="Certificates_Report"> </a>

O relatório de certificados contém todos os certificados que são necessários no Skype recomendada para implantação de negócios Server 2015. As contas da ferramenta de planejamento para os nomes de assunto e os nomes de entidade alternativos que foram inseridos. O texto padrão que é mantido sem edição pode representar um desafio potencial para a equipe responsável pela solicitação e emissão dos certificados. As informações do certificado também incluem informações sobre o local de onde o certificado pode ser normalmente emitido. Se a infraestrutura não tiver uma infraestrutura de chave pública interna (PKI), todos os certificados poderão ser solicitados por meio de um provedor de certificados público. Os campos EKU (Uso Estendido de Chave) e Atribuir a do relatório são muito úteis para ajudar a compreender quais devem ser a finalidade e a localização de cada certificado. 
  
![Relatório do administrador de certificados](../../media/Certificates_Report_Admin_Report.png)
  
Leia com atenção e compreenda o uso e a finalidade de cada certificado na implantação. Se houver uma dúvida sobre o que faz um certificado, determine qual servidor ou serviço está se comunicando com o que. Certificados no Skype para Business Server 2015 são usados para dois objetivos principais:
  
- Mutual Transport Layer Security (MTLS) - os computadores envolvidos na comunicação cada apresentam um certificado que prova de sua identidade para outro computador. Isso é conhecido como autenticação de servidor. Comunicação não pode começar até que a identidade do outro computador de confiança de cada computador.
    
- Criptografia - criptografia (Secure Sockets Layer, ou SSL e segurança da camada de transporte ou TLS) é um meio crítico para ajudar a proteger as comunicações, ajuda a assegurar a privacidade e criar um sistema de colaboração e comunicação confiável.
    
## <a name="review-the-firewall-report"></a>Analisar o relatório de firewall
<a name="Firewall_report"> </a>

Skype para Business Server 2015 tem um conjunto potencialmente complexo de regras de firewall. A ferramenta de planejamento reduz a complexidade, gerando um relatório que define detalhadamente todos os requisitos de firewall, com base nos critérios de entrada do designer. O administrador de firewall de TI pode usar esse relatório para configurar e definir as regras necessárias.
  
Do ponto de vista do gerenciamento de firewall, o relatório deve ser revisado cuidadosamente para garantir que não haja nenhum conflito com as regras de firewall existentes e que não hajam políticas ou procedimentos que possam ser violados.
  
![Relatório do administrador do firewall](../../media/Firewall_Report_Admin_Report.png)
  
## <a name="review-the-dns-report"></a>Examinar o relatório de DNS
<a name="DNS_Report"> </a>

O Relatório de DNS que faz parte dos Relatórios do Administrador fornece detalhes sobre todas as entradas recomendadas e conhecidas para o DNS (Sistema de Nomes de Domínio) nas redes de perímetro, internas e externas. Se o designer tiver concluído as edições no diagrama de rede e todos os endereços IP e FQDNs (nomes de domínio totalmente qualificados) estiverem definidos com seus valores de produção, o Relatório de DNS apresentará um excelente recurso de configuração. Este relatório também pode ser usado como um documento para solução de problemas operacionais.
  
![Relatório do Administrador DNS](../../media/DNS_Report_Admin_Report.png)
  
Você deve ter uma revisão detalhada do Relatório DNS feita por sua equipe de gerenciamento do DNS para garantir que não existam erros que possam causem dificuldade durante a implantação ou compliquem uma sessão de solução de problemas.
  
## <a name="see-also"></a>Ver também
<a name="DNS_Report"> </a>

[Analisando os relatórios do administrador](http://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)