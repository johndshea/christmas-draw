Application URL is https://christmas-draw-app.web.app. It is hosted via Firebase hosting. 

The logic of the app exists entirely on the client-side and the state is stored (and updated live) in Firestore. 

Change the "selectedFamily" variable in the code to switch from Schneiders to Sheas.

Firestore database write permissions expire at a certain date. If the app is not working, check that first. 

Because the app matches givers and recipients live, instead of precalculating all the matches and then revealing them one by one, there is an edge case where a giver could end up with no eligible recipients (e.g. only members of their own household or themselves are left as recipients). The code gracefully degrades to allow same-household giver -> recipient pairs in this case, but you could still theoretically end up in a case where someone is giving to themselves because they are the "last one picked". 