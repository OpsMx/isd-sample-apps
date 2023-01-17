annotations

  
This is for the branch spaecification
    
    argocd-image-updater.argoproj.io/git-branch: master
    
This is image that need to be monitor ~v3 check for matching version
    
    argocd-image-updater.argoproj.io/image-list: docker.io/opsmxdev/issuegen:~v3
    
Create a github secret named githubsecret where it need to push the commit in .argocd-source-imageupdatetest.yaml
    
    argocd-image-updater.argoproj.io/write-back-method: git:secret:argocd/githubsecret
